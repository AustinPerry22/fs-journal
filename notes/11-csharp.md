# CSharp
no truthy or falsy values in c#
Console.WriteLine("line")
make sure to declare variable type
double a = 5.55;
float b = 5.5f;
decimal c = 6.543532m;  - use for money
stings are "" only
char are ''

<!-- Array<int> = new Array<int>[3]{1,2,3};  --> arrays in c# bad fixed length can't be modified

List<string> cats = new List<string>(){"Garfield", "Bean"}; -just like js array, count instead of length
cats.Add("Gopher");
cats.Add(11); -cannot add ints becuase type string
string catToRemove = cats.Find( c => c == "Gopher")
cats.Remove(catToRemove)

complex data types are all built in classes

objects exist but we rarely deal with them.

Dictionary<string, int> myDict = new Dictionary<string, int>();
myDict.Add("hello", 4);
myDict.Add("bye", 3);

Dictionary<List<string>, string> - can do this for a dictionary with a key of a list of strings

class Cat{
    string Name;
    int Age;
    string Color;
    public Cat(string name,int age,string color)
    {
        this.Age = age;
        Name = name;
        Color = color;
    }
}

List<Cat> cats = new List<Cat>();
errors in vscode stay there until it is recompliled

in model
namespace applicationName.Models;  - kind of like an export
public class Cat{
    public int Id {get; set;}
    public string Name {get; set;}  -people can change this outside class
    public readonly string Color {get; set;} -people can see this outside class
    private bool Feisty {get; private set;}

    public Cat(int id, string name, string color, bool feisty){
        Id = id ;
        Name = name ; 
        Color = color ; 
        Age = age ;
        Feisty = feisty;
    }
}

in controller
using appName.Services
//data decorators effect the next definition, making our class an API controller with the route " ../api/cats"
[ApiController]
[Route("api/cats")]
public class CatsController : ControllerBase{

    private readonly CatsService _catService;

    public CatsController(CatsService cs){
        _catsService = cs
    }
    [HttpGet("endpoint")]
    public ActionResult<List<Cat>> GetCats(){  -api endpoint so anyone should be able to call it, Action result 200/400 etc.
        try{
            List<Cat> cats = _catsService.getCats();
            return Ok(cats)
        }
        catch (Exception e)
        {
            return BadRequest(e.message);
        }
    }
}

in service
namespace appName.services
public class CatsService{
    private readonly CatsREpository _repo;
    public CatsService(CatsRepository repo){
        _repo = repo;
    }
    internal List<Cat> GetCats(){
        List<Cat> cats = _repo.GetAllCats();
        return cats
    }
}

you can define in the globals the using statments so you don't have to use using in other files

in repository
namespace appName.Repositories

public class CatsRepository{
    private List<Cat> _FakeDb

    public CatsRepository(){
        _FakeDb = new List<Cat>();
        _FakeDb.Add(new Cat(1,"Jeff", "Orange", 5, true));
    }
    internal List<Cat> GetAllCats(){ - internal can only call this function in this project
        return _FakeDb;
    }  
}


in the startup.cs make sure to configure services/repository for the services/repository in use
services.AddScoped<CatsRepository>();  -needs to be on top
services.AddScoped<CatsService>();

functions that return nothing use void

c# can have the same function names if they have different types - overloading


ONCE WE HAVE OUR DB CREATED WE WON"T USE CONSTRUCTORS IN THE MODEL.

in the repository

private readonly IDbConnection _db;
public CarsRepository(IDbConnection _db)
{
    _db = db;
}

internal List<Car> GetAllCars()
{
    string sql = "SELECT * FROM cars;";  - sad spider ;";
    List<Car> cars = _db.Query<Car>(sql).ToList(); -the type takes the rows and turns them into a car
}

to avoid SQL interjection attacks use the stuff below instead of string interpolation.
pass a key value into the query to match and pull
string sql = "SELECT * FROM cars WHERE id = @cardId;"
Car car = _db.Query<Car>(sql, new {cardID}).FirstOrDefault();
return car

to make a multiline string
string sql = @"
    sql stuff
    more sql stuff
    more sql stuff
    more sql stuff
    (@make, @model, @year)
"

run sql in dbsetup then bring over as a string into the repostitory in c#

you can make data types nullable by doing int?
origninal.ImgUrl = updateData.ImgUrl ?? origninal.ImgUrl;  - null checker



WEDNESSDAY

appsetting.Develpoment = where to add auth settings
make sure to create the account table
make sure your base url is correct https  7045

play around in the sql file before just adding stuff to the sql string

FOREIGN KEY (myvalue) REFERENCE othertable(whatitscalledinothertable) ON DELETE CASCADE - if othertable(thing) is deleted then CASCADE, deletes the rows where the thing is the same

SELECT * FROM mytable JOIN othertable;

write out complex sql statments in mutiple lines for clarity/logic stuff

SELECT 
mt.*, ot.name
FROM mytable mt 
JOIN othertable ot 
ON ot.id = mt.creatorId;

start from repository - service - controller - startup for dependency stuff

the singleton is used throughout the entire application the addscoped creates a new instance for the scope of the http methods.

no more virtuals use the class type

-make sure the order is same as where the select is
_db.Query <Album, Acount, Album>(sql, (album,creator)=>
{
    album.Creator = creator;
}) -last argument is the return type of the internal in the list cuase it smooshes the first two together kinda?

to pass in the creator id for posting/editing/deleting use auth0 in the controller

private readonly Auth0Provider _auth0;

[Authorize]
[HttpPost]
in the request make it async <Task<myType>> Create([FromBody] Album albumdata) - task needs to be on async.
{
    try{
        Account userInfo = await _auth0.GetUserInfoAysnc<Account>(HttpContext);
        albumData.CreatorId = userInfo.id
        normal stuff after here
    }
}

return from the service for edits just make sure to save in the repo

services should only talk to their respective repository.

ExecuteScalar will return a single cell instead of a row like Query will.

view models not vue models


public class AccountCollabViewModel : Account
{
public int CollabId {get;set;}
}

MANY TO MANY

for many to many tables
id
relashionship1 id
relashionship 2 id

foreign keys ON DELETE CASCADE

For Posting a many to many
    -return the thing you want back probably a cultist or cult/recipe
    -in the service make sure to get/return the cultist/cult
    -in the repository
        <!-- MAKE A NEW CULTMEMBER -->
        INSERT INTO cultMembers
        (cultId, accountId)
        VALUES
        (@cultId, @accountId)
        <!-- RETURN THE CULTIST make sure to use a class extension on the profile/cult -->
        SELECT cultMembers*, accounts* FROM cultMembers
        JOIN accounts ON accounts.id = cultMembers.accountId
        WHERE cultMembers.id = LAST_INSERT_ID()

        cast your account into a cultist
use user.isAuthenticated instead of account.id

script setup is used for small things without much functionality



Interfaces
-stuff inherits from this and must have these properties, what i want a class to have
-great for when everything has the same stuff ex. repoitem -  id updated at, created at.

IRepository  - always prefaced with I
namespace App.Interfaces;
public interface IRepository<T, Tid>; -make sure the types are vars so you can pass in any type
{
    List<T> Get();      -don't actually write out the methods becuase they are all unique

    internal T GetById(Tid id); -instance of Tid

    T Create(T newData); -instance of type

    public int Update(T updateData);

    public int Delete(Tid id);
}

to use it 
using App.Interfaces;
public class MyRepository : IRepository<MyModel, int>   ctrl . implement new  thing and builds out repo functions

if you delete or change a function it would break the contract and give you error
adding functions doesn't break the contract

Interfaces should not be responsible for instanctiating things.
so no private readonly IDbconnection _db; or stuff like it.
don't use interfaces for services or business logic.

use null check on get by Id

do cool logic in the backend based on account/ etc ex get all things if i own them and not closed or get all things that aren't closed

to join multiple tables use differnet variabiles when using the same table

JOIN - if i can't join anything don't include the row
LEFT JOIN - gets back other stuff but the stuff to join on stuff is null. includes row

COUNT(reports.id) as reportCount - gets the count for the duplicate where the id is the same

GROUP BY (restaurant.id) - groups the restraunt data together so no duplicates 
group by statements go last


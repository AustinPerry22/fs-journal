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


MySQL.org

massive excel spreadsheet
with cols and row
define table before storing data in it

casing doesn't matter


TEXT - uncapped length
VARCHAR(255) -how many bytes
BOOLEAN - true or false
DATETIME - dated
INT
BIGINT
DOUBLE
FLOAT



CREATE TABLE hotdogs(
    id INT AUTO_INCREMENT PRIMARY KEY, -adds 1 to the id every time hotdog is added, primary key organize by id.
    bun VARCHAR (1000),
    date DATETIME DEFAULT CURRENT_TIMESTAMP,
)

needs to be executed to run

INSERT INTO hotdogs
(name)
VALUES
(myhotdog)

SELECT name, data FROM hotdogs;   - gets all names and dates from the table. * selects all columns
SELECT name, FROM hotdogs WHERE 'hasKetchup' = true AND price < 2; 
// - returns the names where the hasketchup column is true AND the price is < 2. AND AND AND.
WHERE description LIKE '%jalapeno%';   - gets stuff where a jalapeno is in the description %-wildcard character.

ORDER BY name DESC -orders the table by decending name
LIMIT 2 OFFSET 1- limits the result to 2 rows, skips the first dog

SELECT  -order matters in sql
    name,
    price
FROM hotdogs
WHERE price < 30
ORDER BY price;

DELETE FROM hotdogs; -deletes entire table
DELETE FROM hotdogs WHERE id = 5;

UPDATE hotdogs
SET price = 5
WHERE id = 1;

UPDATE hotdogs
SET price = price /2
WHERE price > 5;

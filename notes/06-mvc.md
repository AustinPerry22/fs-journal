# MVC
writing with design patterns allows for scalability/working with teams

MVC is a design pattern.
create websites more responsive/active

Model/view/controller

view - html dom stuff to see/hear 
->
controller - takes actions from user\ draws data to dom 
->
service - business logic, stuff that modifies data
->
appstate - where data is stored
<-
model - blueprint of what the data in the appstate will look like

bcw create - creates files, starter template

models be built first
class is like an outline/blueprint, doesn't make a character\object
class MyChar{
    name
    role
    health
    maxHealth

    constructor(newName, newRole, newMaxHealth){  -method that runs anytime you make an instance of the class
        this.name = newName
        this.role = newRole
        this.health = newMaxHealth
        this.maxHealth = newMaxHealth
    }

    myMethod(){
        this.name  - use this inside the class while you would use hobbit.name on the outside
    }

}

    creates an instance/object from the class
let hobbit = new MyChar()

    t

a member is any object/fn/data in a class
this.   is for an class instance to look at itself.


appstate is the place to store ALL of your data

characters = {
    new myClass(args)
}


to refrence different stuff in js. import/export
export var\class\etc

DO NOT WRITE IMPORT STATMENTS OUT LONGHAND
import var\class\etc from filename

the router is in charge of making an instance of the controllers












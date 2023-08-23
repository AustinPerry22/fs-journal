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



1. build model and properties
2. create data using the model in the Appstate
3. create a controller, have controller draw data
4. add interaction to page elements
5. the rest of it....

you don't need to define properties in the model, just need to use in the constructor

constructors can take in the same parameters as class properties
ex.
constructor(name){
    this.name = name
}

write out templates in index then transfer to the template.



router
    to add multiple controllers to a page put in an array on the router.

    when the page loads it looks at the URL and matches it with a path then loads the corresponding controllers and injects the view into the index.html id #router-view


in service at bottom. this allows users not to access the service.
export const ClassName = new ClassName()

/** @type {Data Type} this is a comment*/  - put above a null variable to allow use to use intellisense

in constructors you can add listeners - when something changes do something
ex.
Appstate.on('myVar', this.myFunc)

ctrl . to create a method in where you are referencing

Appstate.emit('property') - forces the listener for the property to trigger

to use local storage create classes using data objects.

in constructor of model pass in objects for local storage+forms

to make a private function move it outside of the class and use _nameConvention

Forms
-use bootstrap elements 4 now, but not just their default form.
look at docs for elements to use
to submit form have button have type of 'submit'
<form onsumbit="">  - calls functions when submiting form

name property on form input   <input name ="jeff">

window.event.preventDefault() - prevents stuff from refreshing on submit
required property makes it required to fill out./ other stuff like minLength, etc.
const formEvent = window.event.target - grabs the form elem from on submit 

const formData = getFormData(formEvent) is the same as
                                            |
                                            v
const formData = {
    key: form.name.value
    key: form.name.value
    jeff: form.jeff.value  - value is what the user puts in.
}

names should be the same as the object properties you want to store the values in

use save functions to save stuff
saveState('bannana', AppState.stuff) - utitlity function instead of JSON.stringify, etc.

myStuff = loadState('key', [classname])

make id's on objects so you can refrence them better
this.id = generateId() 






















# Node
node reads and runs javascript

express is a framework for node servers

middleware before the (doors) to format/translator/authorization etc, runs and formats before entering.

controller where the request first enters
router is used to route the request

service is still business logic and saving/handling data to the database

model creates a structure for the data to be saved into the database

controller - needs inheritance V - inherits properties from the other class but also has its own properties
export class ControllerName extends BaseController{  -basecontroller says hey this is a hallway
    constructor(){
        super('api/cats')  - run the constructor of BaseController, what sign on the door
        this.router - small hallway off the big hallway
        .get('', function)  - when someone uses get on api/cats
    }
}

- request is object representing incoming request, response is object to manipulate/use to send responses,
next is how we kick people back to the hallway.
function(request, response, next){
    response.send('your data/body')
}

logger.log('log') -console.log doesn't get eaten









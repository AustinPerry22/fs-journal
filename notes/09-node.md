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


model

export const mySchema = new Schema(
    {
        property: String,
        property: {type: String, required: true, minlength: 3, maxlength: 15}
        property: {type: Number, required: true, min: 1, max: 999, }
    }
)


in the dbContext.js

MyName = mongoose.model('name', mySchema)


key: {type String, enum:['only', 'takes', 'these', 'strings']}

in controller in the get/create/etc request

const query = req.query   - gets the query from the request

exhibitId: {type: Schema.Types.ObjectId, ref: 'Exhibit', required: true}  - comes from the database(objectID) and references an id specifically from the Exhibit collection
Exhibit string matches string in the db.context

a virtual gets computed then populated back onto the object - similar to a getter

in schema
    {timestamps: true, toJSON: {virtuals: true}}

    outside of class
    AnimalSchema.virtual('exhibit',{
        localField: 'exhibitId', 
        ref: "Exhibit"
        foreignField: '_id',
        justOne: true
    })

in service get/post/etc .populate('exhibit', 'property property') - default returns whole obj, property only returns those properties

RESTful api conventions is the best practice form naming endpoints etc








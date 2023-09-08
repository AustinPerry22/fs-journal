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
    {timestamps: true, toJSON: {virtuals: true}}  - enable time created, allows virtuals to exist

    outside of class
    AnimalSchema.virtual('exhibit',{   -name of virtual
        localField: 'exhibitId',    -what you are refrencing in the class, usually the other object Id
        ref: "Exhibit"              -What schema your refrencing
        foreignField: '_id',        -what the key is on the shcema your refrencing
        justOne: true               - if this isn't here will return an array with 1 object in it.
    })

in service get/post/etc .populate('exhibit', 'property property') - default returns whole obj, property only returns those properties

RESTful api conventions is the best practice form naming endpoints etc

never trust ownership id's from the client 

to use middleware goes vertically in router throught the middleware to be able to use the post request
.use((req, res. next)=>{
    do what you want
    req.next()
})
.post

to use Auth0 middleware
.use(Auth0Provider.getAuthorizedUserInfo) if has token all good, if no token 401, unauthorized
tacks on userInfo, the userInfo.id should == account.id

you can authorize postman collection in the auth tab with the token

to hide emails/stuff in the populate use populate('id id id...', 'key key key') or ('id id', '-keyIdontWant')




lecture - animations/styling

container fluid in templates
style: overflow hidden on parent div will get rid of overfloww - last resort

css                                     v happens once. infinite is continuous
animation: fadeIn 2s ease-in-out 2s forwards
opacity: 0 - starts invis         ^how long til it starts


@keyframes fadeIn{
    0%{     - 0%at start
        opactiy: 0;
    }
    100%{
        opacity: 1;   - stays at this opacity after the 2s.
        pointer-events: none; - wont be clickable
    }
}

fadeOut would be the opposite

transform: translateX(-100%) - moves the property to the left by 100%, off the page
                        (0%) - orignal position
use overflow-X hidden on parent so no side scroll on the row.

pseudo class selectors ::before and ::after
inserts content before/after element 
content: ''; text before/after elem
top: 5em;
right: 0%;
width: 100% - of the element
height: 100% - of the element

transform: perspective(1em) rotateX(40deg) scale(1, .35)- perspective first

animatebackgrounds.me free animated background
see some cool stuff on other websites yoink with the elem selector

scrolling image use repeat with big img - super high def img.
background-position in keyframes to move around image

even keyframes for smoother animations

60, 120sec good for background effects, too fast is too distracting from main content

alternate on animation goes from 100 to 0 if infinite 0-100-0-100

dont be afraid to break stuff when animating can learn cool stuff.

color psychology
    right amount of color for urgency
    60-30-10
















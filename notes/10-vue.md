r# Vue

front end framework

hot module reloading only reloades the module - on save
sometimes it breaks
turn off autosave


package.JSON - where dependencies go

src is the code part everything else is config

main.js loads App.vue and router
register globalcomponets registerts the componets 

controllers have been replaced with a component 
components is a controller and view kinda
javascript html and css in the same file

much smaller and more targeted to the indiviual component

v-    - view attribute
@click - shorthand for v-bind:click - or onclick
: - can be shorthand

router-link used instead of an a tag

>80 lines of code way to much need to refactor.

js goes in <script></script>
    computed - get acsesses if changes update template, similar to a listener
    no draw or constructor, vue does that
    needs export or export default


style goes in <style></style>

you can refrence other components in components like
<component/>

pages are just components just where you would put your other components

app.vue has the header and footer and main


to use a var in template
must return the var and refrence {{var}}  - {{}} double bind, mustache unwraps object so dont need health.value

@click="function()"

to make something reactive multiple ways
    1. in component - not recomended
        import {ref} from 'vue'    -makes object
            let var = ref(100)
            var.value--  - object that has a value property

    2. in app state
        import {reactive} from vue
            health = 100
to get parameters they are called props


lifecycle hooks
onMounted(function) - runs when mounted/ brought into doc. Make sure function is defined outside of return
-also can use ()=>{} inside to run multiple stuff
onUpdated() - runs when updated
onUnmounted() - runs when unmounted/ removed

define function outside return then add function name in return.

movies: computed(()=> Appstate.movies) - any time we use movies its reactive


in the router.js, can make new routes and link component/page to it

NOTE used when clicking something take to new page, generally use these ones
<router-link :to="{name: 'nameFromRouter.js'}> </router-link> - is like an a tag wrap around thing to click on

NOTE router push should be used only for auto navigating the user when certain processes are done
to change route in functions use
    router = useRouter()
    function(){
        router.push({name: 'nameFromRouter.js'})
    }

above setup and below export default use your props
props: {car: {type: Car, required: true}}

to pass in props in the parent component/page
<MyComponent :car="car" :id="car.id" etc./> -

scss
&:hover{

}

in routerlink :to"{name: 'CarDetails', params: {carId: car.id}}""
in router when clicked on certain car
path: '/cars/:carId', -need to pass in carId so it can link to the correct carid page
name: 'CarDetails',
components: CarDetailsPage

PAGES NEVER TAKE IN PROPS!!!

to get id out of url
const route = useRoute()   - where you are right now/url
route.params.carId  - gets the carId out of the url

service
async getCarById(){
    Appstate.activeCar = null   - sets the active car to null so while its awaiting doesn't show wrong car
    res = await blah blah
}

in css v-bind(variable)
cant do url(v-bind(backgroundImg))
must pass in url(backgroundimgurl) string
then
v-bind(backImg)

<slot name="header">
default view if there is no header template
</slot> in ModalWrapper. can have multiple slots with name
in page
<slot name="body">
default view if there is no body template
</slot> in ModalWrapper. can have multiple slots with name
in page
<ModalWrapper> 
<template #header>
        hello   - can and should be another component but can pass in anything
    </template>
    <template #body>
        hello   - can and should be another component but can pass in anything
    </template>
</ModalWrapper>

watchEffect(()=>{  -will run when inner values change
    Appstate.account
    edible.account = Appstate.account
})



do not change postman test content. they are written to test your backend
- cant start with get cause no content

backend review
-schema, no constuctor

{type: Sting, lowercase: true}  - makes all the string lowercase when passed in.

remember to give bearer token to postman

.populate should be on end of line in a find request and after the request in create/edit

services can call functions in other services


.sort in backend ('-property') sorts the stuff in reverse order

use user.isAuthenticated instead of account.id for v-if's because it is sent before the account

aspect-ratio on images great for height

AlbumsSchema.virtual('memberCount', {
    localField: '_id',    - look at my unique identifier in this document
    foreignField: 'albumId', -look at the album id on the the other document
    ref: 'Collaborator', - the other document
    count: true  - creates a number for each of the matching documents. each collab with and albumId that matches this _id
})
  - do not do this yet
.populate({path: 'album', populate: {path: 'creator membercount', select: '-email'}})  populate inside a populate

to see if user is athenitcated use authservice and run stuff





mini lecture #1  - postman tests
    variables - use them in the top folder and use them like {{myvar}}
    use the bearer token as a variable and do authorization for each call needing a token

    tests are just javascript
        pm - tools that postman has built in
        pm.expect(res.code).to.be.oneOf([200, 201], 'message')
        pm.expect(body.variable).to.be.eql('')
    prerequests - javascript that runs before the request

mini lecture#2 - vue tour
    install in client folder - npm i vue3-tour
    in mainjs - import Vue3Tour from 'vue3-tour'
                import 'vue3-tour/dist/vue3-tour.css'
            under .use(router)
                  .use(Vue3Tour)
    in page 

    on element use id to target it
    at bottom of template
    <v-tour name="myTour" :steps="steps" :callbacks="tourCallBacks">

    </v-tour>
    in return
        steps:[{
            target: {id: 'myElementId'},
            header:{title: 'my header'},
            content: 'here is the step component',
            actions: {next: '<button>click me for next step</button>'},
            params: {placement:'top'}
        },
        --other steps
        ],

        tourCallBacks:{   -built in methods
            onFinish: (()=>{
                stuff you want to happen here like push to anthter page
                router.push({name:'myotherPage'})
            })
        }
    in script tag outside of setup
    mounted: function(){
        this.$tours['myTour'].start()
    }

    to make tour a component use props of steps and callbacks in template use v-tour
    use the mounted in the component also
    build the steps in the return of the page with the component on it

    in the accound schema make a needsTour boolean
    in the account controller backend make an update account method
    in the sanitize body method add needsTour
    in the onfinish method also the onSkip method in the tourCallBacks edit account with needsTour: false
    make sure to add needsTour to model and set the response to the appstate in account
    on v-tour use v-if="account.needsTour" make sure to make account computed

    MAKE SURE TO MAKE THE V-TOUR A COMPONENT


mini lecture#3 - sockets
    -opens a direct connection to server back and forth communication, no requests needed
    -most network communication uses sockets

    -in env.js use sockets = true
    in network tab WS is where websocket stuff is
        green messages your sending to server, red server sending to client
    client has socket service and handler
        -dont worry about socket service yet
        handler is our stuff - similar to a controller
            -looks for a message
            super(io, socket)
            this
                .on('messagenmae', function)
        no async becuase no need to wait for message

        to send messages from client use socketService.emit('messagename', payload) - must be same message as in the service

        in the server the testHandler
            .on('messagename', function)
            this.socket.emit('MEssage', 'booo!')
        to message stuff from anywhere in the server
        socketProvider.message('message', payload)

        socketProvider.messageUser(userId, 'message', payload)

        socketProvider.messageRoom('room' , 'message', payload) only people in the room
        -you are joined into a room with your own id when logged in.


        make a Room handler
            extends sockethandler
            .on('JOIN_Room' this.onJoinRoom)
            .on('leaveRoom', this.leaveroom)

            onJoinRoom(roomname){
                this.socket.join(roomname)
                this.messageUser(userId, 'Joined')
            }
            onLeaveRoom(roomname){
                this.socket.leave(roomname)
                this.messageUser(userId, 'Left')
            }

        rooms are for some messages for people but not all messages
        to join room
        socketProvider.message('JOIN_Room', roomname)
        socketProvider.message('leaveRoom', roomname)

        no longer need to do push res.data from post/put requests to appstate or else it will have 2








        



























wednesday resume time
functional resume
proofread resume
use numbers and stats to quantify
keywords and terms
projects


dont have bad grammer/typos
    professional email
    bullet points
    no photo
    no color
    always save and upload as a pdf
soft and hard skills



cover letter is job specific

canva - use to build resume












            




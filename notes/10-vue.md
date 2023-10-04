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


mini lecture#3 - sockets



























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












            




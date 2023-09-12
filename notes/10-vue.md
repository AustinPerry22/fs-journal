# Vue

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
onUpdated() - runs when updated
onUnmounted() - runs when unmounted/ removed

define function outside return then add function name in return.

movies: computed(()=> Appstate.movies) - any time we use movies its reactive




            




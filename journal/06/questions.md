# Single Page Applications with Vue
01. What is the entrypoint of an application?

  > main.js is the entrypoint for vue applications, this is where the javascript is first run.

02. What is the difference between a vue `component` and `page`?

  > A view component is html, css, and js that is self containing and can be injected onto a page. A page is html, css and js that contains components.

03. What is ***Component-Based Architecture***?

  > Component based Architecture is a way to encasulate pieces of an application into its own component. That way each component can be self sustaining and easy to reuse.

04. What are the three tags that make up a Vue component?

  > The three tags that make up a Vue component are the template, script and style.

05. What are ***lifecycle hooks***? What are lifecycle hooks used for?

  > Lifecycle hooks are similar to listeners in that they run when something happens(component created, updated, destroyed, added to DOM)

06. Which component in Vue does the vue-router use to mount pages onto?

  > The Vue uses the <vue-router></vue-router> componenet to mount the pages onto.

07. What is the difference between the `AppState` and the state object within a component?

  > Appstate Stores data for the whole app to use. The state object is only for the component to use.

08. What is the responsibility of `Services` in our Vue projects?

  > The services responsibility is to change data in the Appstate and handle functionality.

09. What are ***props*** and how are they used? Provide an example

  > Props are passed into a component for that component to use, similar to parameters/arguments in a function. One way they could be used is if you need to access a variable on a parent component, but that is not shared to the Appstate.

10. What is the Vue method used to create watchable objects such as `state` or `AppState`?

  > The vue method used to create a watchable object is computed(). this will look for changes and update accordingly.

# Managing the Fullstack Application

1. Describe the two ways to bind Data in Vue?

  > The two ways of data binding in Vue are one way data binding and two way data binding. One way data binding is used by adding a colon before and attribute ex :class="myVar" the variable is added to the elements class list. Two way data binding is acsessed by using the v-model and can accsess and input data, usually from a form.

2. The `SPA` acronym stands for what?

  > SPA stands for single page application. The site dosen't change the actual page, it uses a router to dynamically change what the user is looking at.

3. What are some of the advantages/uses of a `SPA` over a traditional one?

  > Some advantages of SPA over a traditional site are faster responses, easier debugging, and higher stability.

4. What does the `onMounted` method in Vue do?

  > OnMounted is a vue method that runs when the page is mounted by the router. Kind of like when the page loads this runs.

5. What is the `v-model` attribute in Vue for, and when might you use it?

  > The v-model attribute in Vue is used for two way data binding. You might use it on forms in order to store the inputs and be able to accsess them.

6. What is the package.json file used for?

  > The package.json file is used for listing the dependencies used in the project along with other information like version, name, etc. To install the dependencies you have to run npm i. This allows the project to decrease in size so it can be uploaded to github/ other hosting platforms more efficiently.

7. Which Vue attributes(directives) could you use to conditionally render elements on a page?

  > The vue attributes you could use to conditionally render elements on a page are v-if and v-for. v-show still loads the element into the page, however it hides it while v-for and v-if don't render the element at all.

8. What is the purpose of the `key` attribute when using `v-for` on an element?

  > The purpose of the key attribute when using v-for is to be able to tell multiple elements apart from each other. If there was no key there would be no way for vue to know which element it needed to accsess.

9. What is the `<slot>` element and what is it used for?

  > The slot element is an html element that provides an area for a template to be injected into. It is used for adding custom templates to vue components and allowing them to be more flexible and reusable.

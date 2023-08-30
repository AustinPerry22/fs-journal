# Understanding Asynchronous Code, and API's
01. What is the difference between `asynchronous` code and `synchronous` code?

  >  Synchronous code is code that runs when it is called. Asynchronous code runs when a process is completed ex. downloading.

02. What is an event listener?

  > An event listener runs a function when a variable changes. Ex. when myVar is reassigned (myVar = 1), the listener would run the function in its parameter.

03. What does *REST* stand for, and in simple terms what does it mean??

  > REST stands for Representational state transfer. It's an guideline that shows how API's should connect.

04. What is a callback / higher order function?

  > A callback function is a function that a higher order function calls. A higher order functions receives a callback function as an argument and invokes the callback function in the higher order function.

05. What is a `promise`? How do you capture an error from a `promise`?

  > A promise is an object with 3 states. The initial state(before its called), the resolved state(the promise was completed), and the rejected state(the promise failed). If the info was recieved the promise is completed if not it's rejected.

06. Name three processes used to make requests over `HTTP`?

  > GET, POST, PUT are three process's used to make requests over HTTP. They are used to get data, make new data, and change data.

07. What does the `API` acronym stand for?

  > API stands for Application Programming Interface. It is a way for a programs to connect to each other.

08. What must you do in order to `await` a promise inside of a function?

  > The function must be async in order to await a promise.

09. What is the purpose of encapsulation in programming?

  > The purpose of encapsulation in programming is to only give access to certain functions/properties to users. This makes sure that only certain people can edit/delete/etc certain things. 

10. What is `HTTP` response code for a successful request?

  > A HTTP response code for a successful request is 200 OK.

11. What is a 400 error?

  > Error 400 is a bad request. It means the server can't process information because of a client error.

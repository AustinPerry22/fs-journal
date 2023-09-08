# Intro to Server side concerns with JavaScript
01. What do the letters of the acronym `CRUD` stand for?

  > CRUD stands for Create, Read, Update, and Delete. These methods are used from http requests.

02. Each action that `CRUD` represents maps to an HTTP request. What HTTP request does each `CRUD` action correspond to?

  > Create - post. Read - get. Update - put. Delete - delete.

03. What does `ORM` stand for? Which `ORM` do we use when interacting with MongoDB

  > ORM stands for Object Relational Mapping. We use mongoose to interact with MongoDB.

04. Which two `HTTP` request types include a body?

  > Put and Post include a body because you need to tell what you are updating/ creating. while delete and get you don't need to make changes to the body

05. In a/an _______ coding model, when you call a function, it returns only when the action has finished and stops your program for the time the action takes. Likewise in a/an _______ coding model, multiple things are allowed to happen at one time. When you perform an action, your program continues to run.  Fill in the blanks.

  > Asynchronous. Synchronous.

06. What are the three types of data relationships? Provide an example of each.

  > The three types of data relashionships are one to one, one to many and many to many. One to one ex. One Car has One Engine. one to many ex. One car can have Many wheels. Many to many ex.  a BodyShop, a car can be worked on by Many mechanics and a mechanic can work on Many cars.

07. What is middleware?

  > Middleware is software that is run before the api connects with the client, ex auth0.

08. The ______ pipeline delivers information from the client while the ______ pipeline returns it. Fill in the blanks. 

  > Request. Response.

09. Demonstrate the pattern that is used to include a request query with the client's `HTTP` request providing the property `tag` and the value `winter`.

  > ?tag=winter

10. What is a ***virtual property***?

  > A virtual property is a property that isn't stored in the database, it is computed when you access it.

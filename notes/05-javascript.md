# JavaScript
Name variables as exact as possible

Primative data types - when primitives are passed, they move their value to a new separate source.
	 floats only(no int,complex, etc.) str, bool, noValue(not null)
	
	noValue is undefined doesn't know its value, null knows there is no value
	NaN - not a number
` ` strings can be broken into multiple lines

Reference data types  - when reference types are passed they share the same source.
	Arrays, store values by position (index)
	Objects, store data using key: value pairs, no posistion
	
	
Functions - blocks of code to store and run later
	Function myFunc(myParam, myParam2){      -params are like mad libs spaces
		Return myParam + myParam2
	}
	
	myFunc(1,2)  - returns 3.      1 and 2 are arguments.


/*region*/
/*region*/   - collapse a reagon of code 


To hook up a function to an event handler in html
Event handler ="myFunc()"

Document.getElementById('id')    - gets the element from the dom.

.classlist - can remove or add classes to and element 


Const - creates a variable that is immutable(can't change)


Array methods
	.length - the length of the array
	.forEach() - takes in a callback function (a function that will be fun). Runs it for each item in the array.
	.filter() - creates an array of items that meet the condition.
	.map() - creates an array of the transformed results from the function.
		Ex.   fullName = myArray.map((myObject) => myObject.name + myObject.lastName)
			Returns [firstlast, …]
	.join() - turns elements in array into a string and adds in your seporator(whats the string in here) between each index.
	.find() - finds the first element based on the condition.

*shorten array[i] to a var for easier use in loops and stuff.




Functions
	To invoke a function inside a function use 
		myFunc(func){
			Func();
		}
		myFunc(otherFunction);
		
	To run a function and get the return value to use in another function invoke it
		myFunc(myOtherFunc());
	
	Anon function(lambda) - a function that isn't saved.     .forEach(() => {do this.})
		-to pass use parameters use .method((param) => {do this})
		*if your function only needs 1 param don’t need ().
		
		
	Random  .random does 0-1    uses  .00000008965
	For random int
Math.floor(math.random() * maxint)          


put script tag at end of body

write pseudoscope in comments.

code small test small

hard code in html first before injecting html with javascript

setInterval(myFunc, delay)  - calls a function after a delay forever. delay in ms. don't invoke func.

switch(var){
    case value:
        do stuff
        break   - breaks out the of the switch statment
    case value
        do stuff
        break
    case value
        do stuff 
        break
}


# Intro to JavaScript
01. Which keywords are used to declare a variable in JavaScript?

    > var, let, and const are used to declare variables in javascript.

02. What is the definition of a function?

    > A function is a part of the program that carries out a specific task.

03. What are the `SOLID` principles?

    > The solid principles are 5 important principles to follow when using object oriented programming. They are, the Single responsibility principle, the Open-closed principle, the Liskov subsitution principle, the Interface segregation principle and the Dependancy inversion pricipel.

04. Given this array: How could you remove the `pineapple`?

    ```js
    let fruit = ['apple', 'banana', 'pineapple', 'orange', 'strawberry']
    ```

    > fruit[2].pop()

05. Given these two objects: How could you add each to the others friends arrays?

    ```js
    let you = {
        name: "You",
        hair: true,
        friends: []
    }
    let them = {
        name: "Them",
        hair: false,
        friends: []
    }
    ```

    > you.friends.push(them)        them.friends.push(you)

06. Give an example of a JavaScript `Conditional`:

    > an if statement is a conditional in js. 

07. What is the main difference between `parameters` and `arguments`?

    > Parameters are used when defining a function to tell it what type of arguments it will have. Arguments are values that are passed into the function.

08. Instead of writing everything to the console, what is a better way to debug your code?

    > Using breakpoints can be a very helpful way to debug your code because you get to see when an error is thrown and better understand why because you can go through it step by step.

09. What is the difference between a `primitive` value and a `reference` value?

    > A primitive value contains the actual string, number, bool, while the reference value points to the string, number, bool in memory.

10. Demonstrate a loop that prints the numbers between -100 and 100?

    > for(i=-100; i<=100; i++){
        console.log(i);
    }

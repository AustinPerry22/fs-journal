# CSharp and SQL Fundamentals
01. What is the purpose of a `namespace`?

  > The purpose of a namespace is to allow other files to access the functionality from the class.

02. What is the difference between a `class` and an `interface`?

  > A class can have class methods on it with properties, an interface has method declarations, but no definitions. An interface is used mostly to connect one thing to another.

03. What is the method that returns an instance of a class, yet it has no return type?

  > Void is the method that returns an instance of a class with no return type.

05. In the Car example what is the access modifier of the `Start()` method?

  ```c#
  abstract class Car
  {
    public string Start()
    {

      return "Vroooom";

    }
  }
  ```

  > The access modifier is public in the start method, becuase it can be accsessed from anywhere.

06. In the Car example what is `string` an indication of?

  > string is an indication of the return type.

07. In the Car example what is `abstract` preventing?

  > Abstract prevents objects from being created from the class.

08. In a SQL table, what is the difference between information in a row and information in a column?

  > The information in a row is like an instance of a class, meaning it has mutliple connected properties
  > The information in a column is like the attributes of the object.

09. Demonstrate the necessary SQL for creating a table called `characters` with the values `name, age, description` as strings, and an `int` id.

  > CREATE TABLE characters (
    name VARCHAR(25)
    age VARCHAR(10)
    description VARCHAR(255)
    id INT()
  )

10. In SQL how can you query more than a single table? Provide an example.

  > no idea

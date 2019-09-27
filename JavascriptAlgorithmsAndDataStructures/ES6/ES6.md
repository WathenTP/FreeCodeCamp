# ES6

## Introduction to the ES6 Challenges

ECMAScript is a standardized version of JavaScript with the goal of unifying the language's specification, the term ECMAScript is interchangeable with the term JavaScript.

Most of the challenges on freeCodeCamp use ES5 specification of the language, finalised in 2009. But JavaScript is an evolving programming language. As features are added and revisions are made, new versions of the language are released for use by developers.

The most recent standardised version is called ES6, released in 2015. This new version of the language adds some powerful features that will be covered in this section of challenges, including:

- Arrow Functions
- Classes
- Modules
- Promises
- Generators
- let and const

Note
Not all browsers support ES6. If you use Es6 in your own projects, you may need to use a program (transpiler)to convert your ES6 into ES5 until the browser supports ES6.

## Explore Differences Between the var and let Keywords

One of the biggest problems with declaring variables with the var keyword is that you can overwrite variable declarations without an error.

    var camper = 'James'
    var camper = 'David'
    console.log(camper);
    // logs 'David'

As you can see in the code above, the camper variable is orginally declared as JAmes and then overridden to be David.

In a small application, you might not run into this type of problem, but when your code becomes larger, you might accidentally overwrite a variable that you did not intend to overwrite.

Because this behaviour does not throw and error, searching and fixing bugs becomes more difficult.

A new keyword called let was introduced in ES6 to solve this potential issue with the var keyword

If you were to replace var with let in the variable declarations of the code above, the result would be an error.

    let camper = 'James'
    let camper = 'David'
    console.log(camper);
    // throws an error

So unlike var, when using let, a variable with the same name can only be declared once.

Note the "use strict". This enables Strict Mode, which catches common coding mistakes and "unsafe" actions. For instance:

    "use strict";
    x = 3.14; // throws an error becuase x is not declared

## Compare Scopes of var and let Keywords

When you declare a variable with the var keyword, it is declared globally, or locally if declared inside a function.

The let keyword behaves similarly, but with some extra features. When you declare a variable with the let keyword inside a block, statement or expression its scope is limited to that block, statement or expression.

for example:

    var numArray = [];
    for (var i = 0; i < 3; i++) {
      numArray.push(i);
    }
    console.log(numArray);
    // returns [0, 1, 2]
    colsole.log(i);
    // returns 3

With the var keyword, i is delcared globally. So when i++ is executed, it updates the global variable. This code is similar to the following:

    var numArray = [];
    var i;
    for (i = 0; i < 3; i++) {
      numArray.push(i);
    }
    console.log(numArray);
    // returns [0, 1, 2]
    console.log(i);
    // returns 3

This behaviour will cause problems if you were to create a function and store it for later use inside a for loop that uses the i variable. This is because the stored function will always refer to the value of the updated global i variable.

    var printNumTwo;
    for (var i = 0; i < 3; i++) {
      if(i === 2) {
        printNumTwo = function () {
          return i;
        };
      }
    }
    console.log(printNumTwo());
    // returns 3

As you can see, printNumTwo() prints 3 and not 2. This is becuase the value assigned to i was updated and the printNumTwo() returns the global i and not the value i had when the function was created in the for loop. The let keyword does not follow this behaviour:

    "use strict";
    let printNumTwo;
    or (var i = 0; i < 3; i++) {
      if(i === 2) {
        printNumTwo = function () {
          return i;
        };
      }
    }
    console.log(printNumTwo());
    // returns 2

i is not defined because it was not declared in the global scope. It is only declared within the for loop statement. printNumTwo() returned the correct value becuase three different i variable with unique values (0, 1 and 2) were created by the let keyword within the loop statement.

## Delcare a Read-Only Variable with the const Keyword

let is not the only new way to declare variables. In ES6, you can also declare variables using the const keyword.

const has all the features that let has with the added bonus that variables declared using const are read only. They are a constant value, which means that once a variable is assigned with const it cannot be reassigned.

    "use strict"
    cont FAV_PET = "Cats";
    FAV_PET = "Dogs" // returns error

As you can see, trying to reassign a variable declared with const with throw an error. You should always name variables you don't want to reassign using the const keyword.

This helps when you accidentally attempt to reassign a variable that is meant to stay constant. A common practice when naming constants is to use all uppercase letters, with th ewords seperated by an underscore.

## Mutate an Array Declared with const

The const declaration has many use cases in modern JavaScript.

Some developers prefer to assign all their variable using const by default, unless they know they will need to reassign the value. Only in that case, they use let.

However, it is importatn to understand that object (including arrays and functions) assigned to a variable using const are still mutable. Using the const declaration only prevent reassignment of the variable identifier.

    "use strict"
    const s = [5, 6, 7];
    s = [1, 2, 3]; // throws error, trying to assign const
    s[2] = 45 // works just as it would with an array delcared with var or let
    console.log(s); // returns [5, 6, 45]

As you can see, you can mutate the object [5, 6, 7] itself and the variable s will still point to the altered array [5, 6, 45]. Like all arrays, the array elements in s are mutable, but becasue const was use, you cannot use the variable identifier s to point to a different array using the assingment operator.

## Prevent Object Mutation

As seen in the previous challenge, const declaration alone doesn't really protect your data from mutation. To ensure your data doesn't change, JavaScript provides a function Object.freeze to prevent data mutation.

Once the object is frozen, you an no longer add, update or delete properties from it. Any attempt at changing the object will be rejected without an error.

    let obj = {
      name: "FreeCodeCamp",
      review: "Awesome"
    };
    Object.freeze(obj);
    obj.review = "bad"; // will be ignored. Mutation not allowed
    obj.newProp = "Test"; // will be ignored. Mutation not allowed.
    console.log(obj); // name: "FreeCodeCamp", review: "Awesome"

## ES6: Arrow Function to Write Concise Anonymous Functions

In JavaScript, we often don't need to name our functions, esepcially when passing a function as an argument to another function. Instead, we create an inline functions. We don;t need to name these function because we do not reuse them anywhere else.

To achieve this, we often use the following syntax:

    const myFunc = function () {
      const myVar = "value";
      return myVar;
    }

ES6 provides us with the synaptic sugar to not have to write anonymous functions this way. Instrad, you can use arrow function syntax:

    const myFunc = () => {
      const myVar = "value";
      return myVar;
    }

When there is no function body and only a return value, arrow function syntax allows you to omit the keyword return as well as the brackets surrounding the code. This helps simplify smaller functions into one-line statements:

    const myFunc = () => "value"

This code will still return the value by default.

## Write Arrow Functions with Parameters

Just like normal function, you ca pass arguments into arrow functions.

    // doubles input valuea nd returns it
    const doubler = (item) => item * 2;

You can pass more than one argument into arrow functions as well.

## ES6: Write Higher Order Arrow Functions

It's time we see how powerful arrow functions are when processing data.

Arrow functions work really well with higher order functions, such as map(), filter() and reduce()., that take other functions as arguments for processing collections of data.

Read the following code:

    FBPosts.filter(function(post) {
      return post.thumbnail !== null && post.shares > 100 && post.likes > 500;}
    })

We have written this with filter() to at least make it somewhat readable. Now compare it to the following which uses arrow function syntax:

      FBPosts.filter((post) => post.thumbnail !== null && post.shares > 100 && post.likes > 500)

This code is more succinct and accomplishes the same task with fewer lines of code.

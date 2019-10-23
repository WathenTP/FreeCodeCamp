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

Here is the task:

Use arrow function syntax to compute the square of only the positive integers (decimal numbers are not integers) in the array realNumberArrayand store the new array in the variable squaredIntegers.

Here is the code I have to change:

    const realNumberArray = [4, 5.6, -9.8, 3.14, 42, 6, 8.34, -2];
    const squareList = (arr) => {
      "use strict";
      // change code below this line
      const squaredIntegers = arr.filter((num) => num > 0 && num % parseInt(num) === 0).map((num) => Math.pow(num, 2));
      // change code above this line
      return squaredIntegers;
    };
    // test your code
    const squaredIntegers = squareList(realNumberArray);
    console.log(squaredIntegers);

## Set Default Parameters for Your Functions

In order to help us create more flexible functions, ES6 introduces default parameters for functions.

Check out this code:

    function greeting(name = "Anonymous") {
      return "Hello" + name;
    }
    console.log(greeting("John")); // Hello John
    console.log(greeting()); // Hello Anonymous

The default parameter kicks in when the argument is not specified (it is undefined). As you can see in the example above, the parameter name will receive its default "Anonymous" when you do not provide a value for the parameter. You can add default values for as many parameters as you want.

## Use the Rest Paramter with Function Paramters

In order to help us create more flexible functions, ES6 introduces the rest parameter for function parameters. With the rest parameter, you can create functions that take a variable number of arguments. These arguments are stored in an array that can be accessed later from inside the function.

Check out this code:

    function howMany(...args) {
      return "you have passed " + args.length + " arguments.";
    }
    console.log(howMAny(0, 1, 2)); // you have passed 3 arguments
    console.log(howMany("string", null, [1, 2, 3], {})) // you have passed 4 arguments

The rest parameter elimates the need to check the args array and allows us to apply map(), filter() and reduce on parameters array.

Modify the function sum using the rest paramter in such a way that the function sum is able to take any number of arguments and return their sum.

    const sum = (x, y, z) => {
      const args = [x, y, z];
      return arg.reduct((a, b) => a + b, 0)
    }
    console.log(sum(1, 2, 3)); // 6

Now using the rest paramters

    const sum = (...args) => {
      return args.reduce((a, b) => a + b, 0);
    }
    console.log(sum(1, 2, 3)); // 6

## Use the Spread Operator to evaluate Arrays In-Place

ES6 introduces the spread operator, which allows us to expand arrays and other expressions in places where mulptiple parameters or elements are expected.

The ES5 code below uses apply() to compute the maximum value in an array.

    var arr [6, 89, 3, 45];
    var maximum = Math.max.apply(null, arr); // returns 89

We had to use Math.max.apply(null, arr) because Math.max(arr) returns NaN. Math.max() expects comma-seperated arguments, but not an array. The spread operator makes this syntax much better to read and maintain.

    const arr = [6, 89, 3, 45];
    const maximus = Math.max(...arr); // returns 89

...arr returns an unpacked array. In other words it spreads the array. However, the spread operator only works in-place, like in an argument to a function or in an array literal. The following code will not work:

    const spreaded = ...arr; // will throw a syntax error

Copy all contents of arr1 into another array arr2 using the spread operator:

    const arr1 = ['JAN', 'FEB', 'MAR', 'APR', 'MAY'];
    let arr2;
    arr2 = []; // change this line
    console.log(arr2);

Solution:

    const arr1 = ['JAN', 'FEB', 'MAR', 'APR', 'MAY'];
    let arr2;
    arr2 = [...arr1];
    console.log(arr2);

## Use Destructuring Assignment to Extract Values from Objects

Destructuring assigment is special syntax introduced in ES6, for neatly assigning values taken directly from an object.

Consider the following ES5 code:

    const user = {name: 'John Doe', age: 34};

    const name = user.name; // name = 'John Doe'
    const age = user.age; // age = 34

Here's an equivalent assignment statement using the ES6 destructuring syntax:

      const {name, age} = user; // name = 'John Doe', age = 34

Here, the name and age variables will be created and assigned the values of their respective values from the user object. You can see how much cleaner this is.

you can extract as many or few values from the object as you want.

Replace the two assignment with an with an equivalent destructuring assignment. It should still assign the varialbe today and tomorrow the values of today and tomorrow from the HIGH_TEMPERATURES object.

    const HIGH_TEMPERATURES = {
      yesterday: 75,
      today: 77,
      tomorrow: 80
    };

    // change code below this line

    const today} = HIGH_TEMPERATURES.today;
    const tomorrow = HIGH_TEMPERATURES.tomorrow;

    // change code above this line

    console.log(yesterday) // should be not defined
    console.log(today); // should be 77
    console.log(tomorrow); // should be 80

Solution

    const HIGH_TEMPERATURES = {
        yesterday: 75,
        today: 77,
        tomorrow: 80
      };

    const {today, tomorrow} = HIGH_TEMPERATURES;

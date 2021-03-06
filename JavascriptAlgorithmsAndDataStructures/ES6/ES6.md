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

## Use the Rest Parameter with Function Paramters

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

    var arr = [6, 89, 3, 45];
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

    const today = HIGH_TEMPERATURES.today;
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

## Use Destructuring Assigment to Assign Variables from Objects

Destructuring allows you to assign a new variable name when extracting values. You can do this by putting the new name after a colon when assigning the value.

Using the same object from the last example:

    const user = {name: 'John Doe', age: 34};

Here's how you can give new variable names in the assignment:

    const {name: 'John Doe', age: 34} = user; // userName = 'John Doe', userAge = 34

You may read it as "get the value of user.name and assign it to a new variable names userName" and so on.

Replace the two assignments with an equivalent destructuring assignment. It should still assign the variables highToday and highTomorrow the values of today and tomorrow from the HIGH_TEMPERATURES object.

    const HIGH_TEMPERATURES = {
      yesterday: 75,
      today: 77,
      tomorrow: 80
    };

    // change code below this line

    const highToday = HIGH_TEMPERATURES.today;
    const highTomorrow = HIGH_TEMPERATURES.tomorrow;

    // change code above this line

    console.log(yesterday) // should be not defined
    console.log(highToday); // should be 77
    console.log(highTomorrow); // should be 80

Solution:

    const HIGH_TEMPERATURES = {
          yesterday: 75,
          today: 77,
          tomorrow: 80
        };

    const {today: highToday, tomorrow: highTomorrow} = HIGH_TEMPERATURES;

## Use Destructuring Assignment to Assign Variables from Nested Objects

You can use the same principles from the previous two lessons to destructure values from nested objects.

Using an object similar to previous examples:

    const user = {
      johnDoe: {
        age: 34,
        email: 'johnDoe@freeCodeCamp.com'
      }
    };

Here's how to extract the value of object properties and assign them to variables with the same name:

    const { johnDoe: {age, email}} = user;

and here's how you can assign an object properties' values to variables with different names:

    const { johnDoe: { age: userAge, email: userEmail }} = user;

Replace the two assignment with an equivalent destructuring assignment. It should still assign the variables lowToday and highToday the values today.low and today.high from the LOCAL_FORECAST object.

    const LOCAL_FORECAST = {
      yesterday: { low: 61, high: 75 },
      today: { low: 64, high: 77 },
      tomorrow: { low: 68, high: 80 }
    };

    // change code below this line

    const lowToday = LOCAL_FORECAST.today.low;
    const highToday = LOCAL_FORECAST.today.high;

    // change code above this line

    console.log(lowToday); // should be 64
    console.log(highToday); // should be 77

Solution:

    const {today: {low: lowToday, high: highToday}} = LOCAL_FORECAST

## Use Destructuring Assignment to assign Variables from Arrays

ES6 makes destructuring arrays as easy as destructuring objects.

One key difference between the spread operator and array destructuring is that the spread operator unpacks all contents of an array into a comma-seperated list. Consequently, you cannot pick or choose which elements you want to assign to variables.

Destructuring an array lets us do exactly that:

    const [a, b] = [1, 2, 3, 4, 5, 6];
    console.log(a, b)  // 1, 2

The variable a is assigned the first value of the array and b is assigned the second value of the array. We can also access the value at any index in an array with destructuring by using commas to reach the desired index:

    const [a, b,,, c] = [1, 2, 3, 4, 5, 6];
    console.log(a, b, c) // 1, 2, 5

Use destructuring assignment to swap the value of a and b so that a receives the value stored in b, and b receives the value stored in a:

    let a = 8, b = 6;
    // change code below this line

    // change code above this line
    console.log(a); // should be 6
    console.log(b); // should be 8

Solution:

    [a, b] = [b, a];

## Use Destructuring Assignment with the Rest Parameter to Reassign Array Elements

In some situations involving array destructuring, we might want to collect the rest of the elements into seperate array.

The result is similar to Array.prototype.slice(), as show below:

    const [a, b, ...arr] = [1, 2, 3, 4, 5, 7];
    console.log(a, b); // 1, 2
    console.log(arr); // [3, 4, 5, 7]

Variables a and b take the first and second values from the array. After that, because of the rest paramter's presence, arr gets the rest of the values in the form of an array. The rest element only works correctly as the last variable in the list. As in, you cannot use the rest parameter to catch a subarray that leaves out last element of the original array.

Use destructuring assignment with the rest parameter to perform an effective Array.prototype.slice() so that arr is a sub-array of the original array source with the first two element omitted.

    const source = [1,2,3,4,5,6,7,8,9,10];
    function removeFirstTwo(list) {
      "use strict";
      // change code below this line
      const arr = list; // change this
      // change code above this line
      return arr;
    }
    const arr = removeFirstTwo(source);
    console.log(arr); // should be [3,4,5,6,7,8,9,10]
    console.log(source); // should be [1,2,3,4,5,6,7,8,9,10];

Solution:

      const [a, b, ...arr] = list;

## Use Destructuring Assignment to Pass an Object as a Function's Parameters

In some cases, you can destructure the object in a function argument itself. Consider the code below:

    const profileUpdate = (profileData) => {
      const {name, age, nationaility, location} = profileData;
      // do something with these variables
    }

This effectively destructures the object sent into the function. This can also be done in-place:

    const profileUpdate = ({name, age, nationaility, location}) /* do something with these fields */
    }

This removes some extra lines and makes our code look neat. This has the added benefit of not having to manipulate an entire object in a function - only the fields that are needed are copied inside the function.

Use destructuring assignment within the argument to the function half to send only max and min inside the function.

    const stats = {
      max: 56.78,
      standard_deviation: 4.34,
      median: 34.54,
      mode: 23.87,
      min: -0.75,
      average: 35.85
    };

    // change code below this line
    const half = (stats) => (stats.max + stats.min) / 2.0; // use function argument destructuring
    // change code above this line

    console.log(stats); // should be object
    console.log(half(stats)); // should be 28.015

Solution:

    const half = ({max, min}) => (max + min) / 2.0;

## Create Strings using Template Literals

A new feature of ES6 is the template literal. This is a special type of string that makes creating complex strings easier. Template literals allow you to create multi-line strings and to use string interpolation features to create strings.

Consider the code below:

    const person = {
      name: "Zodiac Hasbro",
      age: 56
    };

    // Template literal with multi-line and string interpolation

    const greeting = `Hello, my name is ${person.name}! I am ${person.age} years old.`;

    console.log(greeting); // prints
    // Hello, my name is Zodiac Hasbro!
    // I am 56 years old.

A lot of things happened there. Firstly, the example uses backticks (`) and not quotes (' or "), to wrap the string. Secondly, notice that the string is multi-line, both in the code and the output. This saves inserting \n within strings. The \$(variable) syntax used above is a placeholder. Basically, you won't have to use concatenation with the + operator anymore.

To add variables to strings, you just drop the variable in a template string and wrap it with ${ and }. Similarly, you can  include other  exrpressions in your string literal, for example ${a + b}. This new way of creating strings gives you more flexibility to create robust strings.

Use template literal syntax with backticks to display each entry of result object's failure array. Each entry should be wrapped inside an li element with the class attribute text-warning, and listed within the resultDisplayArray/

Use an iterator method (any kind of loop) to get the desired output.

    const result = {
      success: ["max-length", "no-amd", "prefer-arrow-functions"],
      failure: ["no-var", "var-on-top", "linebreak"],
      skipped: ["id-blacklist", "no-dup-keys"]
    };
    function makeList(arr) {
      "use strict";

      // change code below this line
      const resultDisplayArray = [null];
      // change code above this line

      return resultDisplayArray;
    }
    /**
    * makeList(result.failure) should return:
    * [ `<li class="text-warning">no-var</li>`,
    *   `<li class="text-warning">var-on-top</li>`,
    *   `<li class="text-warning">linebreak</li>` ]
    **/
    const resultDisplayArray = makeList(result.failure);

Solution:

    for (let i = 0; i < arr.length; i++) {
        resultDisplayArray.push(`<li class="text-warning">${arr[i]}</li>`)
      }

## Write Concise Object Literal Declarations Using Object Property Shorthand

ES6 adds some nice support for easily defining object literals. Consider the following code:

    const getMousePosition = (x, y) => ({x: x, y:y});

getMousePosition is a simple function that returns an object containing two properties. ES6 provides the syntactic sugar to elimate the redundancy of having to write x: x. You can simply write x once, and it will be converted to x: x (or something equivalent) under the hood. Here is the same function from above rewritten to use this new syntax:

    const getMousePosition = (x, y) => ({ x, y});

Use object property shorthand with object literals to create and return an object with name, age, gender properties.

    const createPerson = (name, age, gender) => {
      "use strict";
      // change code below this line
      return {
        name: name,
        age: age,
        gender: gender
      };
      // change code above this line
    };
    console.log(createPerson("Zodiac Hasbro", 56, "male")); // returns a proper object

Solution:

    return {
      name,
      age,
      gender
    };

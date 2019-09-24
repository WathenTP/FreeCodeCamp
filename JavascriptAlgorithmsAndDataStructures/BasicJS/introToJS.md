# Basic Javascript

Commenting code, these are lines of code that JS will intentionally ignore. There are 2 ways to do this in JS either, // or you can comment out multiple lines by beginning with /_ and ending _/.

Comments should regularly be added to clarify the function of parts of your code.

In CS data is everything that is meaningful to a computer. JS provides seven different data types which are: undefined, null, bolean, string, symbol, number and object.

Numbers are defined as 1, 2, 3 etc and strings are a collection of characters “12”, “dog” and “123 cats”. Computers can performs mathematical function on the former but not the latter.

## Declaring JS Variables

Variables, allow computers to store and manipulate data in a dynamic fashion. They do this by using a “label” to point to data, rather than using the data itself. Any of the seven data sets Amy be stored as a variable.

They are similar to the x and y variables you use in mathematics. Which means they’re a simple name to represent data we want to refer too. Computer variable differ however, in that they can store different values at different times.

JS is told to declare a variable by putting the key word var infant of it e.g.

    var ourName;

Creates a variable called ourName, in JS statements end with a semicolon. Variable names can be made up of numbers, letters and \$ or \_ but may not contain spaces or start with a number.

## Storing Values with the Assignment Operator

A value can be stored against a variable with the assignment operator; =, assignment always goes from right to left. Everything right of the = operator is resolved before etc value is assigned to the variable to the left of the operator.

    myVar = 5;
    myNum = myVar;

This assigns 5 to myVar then resolves myVar to 5 then again it assigns it to myNum.

Initialising Variable with the Assignments Operator

It is good practice to initialise a variable to an initial value in the same line it is declared
var myVar = 0;

Creates a variable called myVar and assigns it an initial value of 0.

## Understanding uninitialised variables

When JS variables are declared they have an initial value of undefined, any mathematical operation on an undefined variable will result NaN (not a number). If you concatenate a string with an undefined variable you will get a literal string “undefined”.

## Understanding Case Sensitivity in Variables

In JS all variables and functions are case sensitive. For example MYVAR is the not the same as MyVar. It is therefore possible to have multiple distinct variables with the same name but different casing (however, for the sake of clarity do not do this).

Best practice: Write variables camelCase

## Arithmetic with JS

Number is a data type in JS which represents numeric data. To add two numbers together use the + operator, to subtract use -, to multiple use \*, to divide use /.

A number can be incremented with JS using the ++ operator. For example,

    i++; is the same as writing i = i + 1;

If this is used postfix; i++, then it increments and returns the value before incrementing.

    var x = 3
    y = x++; // y = 3, x = 4

If this is used prefix, ++i, then it increments and returns the value after incrementing.

    var a = 2
    b = a++; // a = 3, b = 3

Decrementing or decreasing a variable by one with the - -, operator.

## Creating decimal numbers with JS

Decimal numbers are referred to as floating point numbers or floats. Floats are speedy and highly efficient, which gives them an advantage. They can deal with enormous numbers and small numbers without needing lots of space.

Floating point numbers have some issues with asccuracy due to the lack of recursion in computing, this video explains it nicely https://www.youtube.com/watch?v=PZRI1IfStY0.

## Finding a remainder in JS

The remainder operator % gives the remainder of the division of 2 numbers. For examples:

    5 % 2 = 1

This is because

    Math.floor(5 / 2) = 2 (Quotient)
    2 * 2 = 4
    5 - 4 = 1 (Remainder)

This is particularly useful to check if a number is odd or even, with odd numbers having a remainder and even numbers having no remainder.

## Compound Assignment with Augmented Addition

Because everything to the right of the = operator is evaluated first it is often common practice to use operators which fo both a mathematical operation and assignment in one step, one such example is the += operator.

For Example:

    var myVar = 1;
    myVar += 5;
    console.log(myVar); // Returns 6

Likewise augmented subtraction can be done with -= operator. multiplication with the \*= operator, division with /=

## Declaring String Variables

    var myName = “your name”;

“your name” is called a string literal, it is a strong because it is a series of zero or more characters enclosed in single or double quotes.

    var myName = “Thom Wathen”;

When defining a string you must start and end with a single or double quote, so when you need a literal quote inside of a string you can escape this issue by placing a backslash in front of the quote:

    var sampleStr = “Alan said, \”Peter is learning Javascript\”.”;

This signals to JS that the quote is not the end of the string and instead should appear inside the string. In JS single and double quotes work the same, which is not the case for some other languages. Remember, a string has the same kind of quote at the beginning and end. But if you have that same quote somewhere in the middle, the string will stop early and throw an error. So for example, using an apostrophe needs to be account for e.g.

    goodStr = ‘Jakes asks Finn, “Hey, let\’s go on an adventure?”’

It is also important to note that the backslash and forward slash should not be confused.

## Escape Sequences in Strings

Quotes are not the only characters that can be escaped inside a string. There are two reasons for seeing exacting characters.
Allows the use of a character you might not otherwise be able to type out e.g. backspace
Allow you to represent multiple quotes in a string without JS misinterpreting what you mean.

    \’ = single quote
    \” = double quote
    \\ = backslash
    \n = newline
    \r = carriage return
    \t = tab
    \b = backspace
    \f = formfeed

## Concatenating strings with the + operator

When the + operator is used with a string value it is called the concatenation operator. You can build new strings out of other strings by concatenating them together. Important to note that concatenation does not add sauces between concatenated strings so you’ll need to add them yourself.

    var myStr = “This is the start. “ + “This is the end.”
    This is the start. This is the end.

Using the += operator to concatenate a string onto the end of an existing string variable. This can be very helpful to break a long string over several lines.

    var myStr = “This is the first sentence. “;
    myStr += “This is the second sentence.” ;

## Constructing Strings with Variables

Sometimes you will need to build a string, Mad Libs style. By using the concatenation operator you can insert one or more variable into a string you’re building.

    var myName = “Thom”;
    var myStr = “My name is “ + myName + “ and I am well!”;
    My name is Thom and I am well!

## Appending Variable to strings

Just as we can build a string over multiple lines out of the string literals, we can also append variables to a string using the += operator.

    var someAdjective = “Awesome!”;
    var myStr = “Learning to code is “;
    myStr += someAdjective;
    Learning to code is Awesome!

## Find the length of a string

This can be done by adding .length after the string variable or string literal.
“Alan Peter”.length; // 10

We can also assign this to the variable itself

    firstName = “Charles”;
    firstName.length;
    7

## Bracket notation

## To find the first character in a string

Bracket notation is a way to get a character at a specific index within a string. Modern programming languages start counting at 0 and not 1. This is referred to as zero based indexing.

    var firstName = “Charles”;
    firstName[0]
    C

## String Immutability

in JS string values are immutable, which means they cannot be altered once they have been created.

    var myStr = “Bob”
    myStr[0] = “J”

This cannot be true as the value of myStr cannot be changed to Job because they cannot be altered once created. This isn’t to say that myStr cannot be changed, however, it would need to assign a new string to do so.
Bracket notation can also be used to find the Nth character in a string
var firstName = “Ada”;
var secondLetterOfFirstName = firstName[1];
d

## To find the last character in a string

In order to get the last letter of a string, yo ucan subtract one from the string’s length. For example

    var firstName = “Charles”
    firstName[firstName.length - 1]
    s

## To find the Nth-to-last character in a string

The same principle is applied as seen above, for example if i wanted the 3rd to last letter.

    var firstName = “Charles”
    firstName[firstName.length - 3]
    l

## Putting it all together!

    function wordBlanks(myNoun, myAdjective, myVerb, myAdverb) {
    	var result = “The “ + myAdjective + “ “ + myNoun + “ “ + myVerb + “ “ + myAdverb + “.”;
    	return result;
    }

    wordBlanks(“dog”, “big”, “ran”, quickly”);
    The big dog ran quickly.

## JS arrays

## Store multiple values in one variable using

With JS array variable, we can store several pieces of data in one place. An array declaration is started with an open square bracket and closed with the closing square bracket, each entry should have a comma between them:

    var sandwich = [“peanut butter”, “jelly”, “bread”];

## Nesting one array inside another

Arrays can also be nested with other arrays, this is also known as multidimensional arrays

    var multidimensional = [[“Thom”, 26], [“Linda”, 27]];

## Accessing Array data with Indexes

Array indexes are written in the same bracket notation that strings use, except that instead of specifying a character they are specifying an entry in the array. Like strings, arrays use zero-based indexing i.e. the first element is 0.

    var array = [50,60,70];
    array[0]; // equals 50
    var data = array[1] // equals 60

## Modifying Array data with indexes

Unlike strings the entries in arrays are mutable and can be changed freely

    var ourArray = [50,40,30];
    ourArray[0] = 15; // results in [15,40,30]

## Access multi-dimensional arrays with indexes

One way to think of multi-dimensional arrays is as an array of arrays. When you use brackets to access your array, the first set of brackets refers to the entries in the outer-most (the first level) array and each additional pair of brackets refers to he next level of entries inside.

    var arr = [
    [1,2,3],
    [4,5,6],
    [7,8,9],
    [[10,11,12], 13, 14]
    ];

    arr[3]; // equals [[10,11,12], 13, 14]
    arr[3][0]; // equals [10, 11, 12]
    arr[3][0][1]; // equals 11

## Manipulating arrays

### .push( )

As easy way to append data to the end of an array is via the push( ) function. This takes one or more parameters and “pushes” them onto the end of the array.

    var arr = [1, 2, 3];
    arr.push(4);
    // arr is now [1, 2, 3, 4]

### .shift( )

Popping removes the last item and shift removes the first item.

    var threeArr = [1, 4, 6];
    var oneDown = threeArr.shift( );
    console.log(oneDown); // Returns 1
    console.log(threeArr); // Returns [4, 6]

### .pop( )

This is used to “pop” a value off of the end of the an array. The popped off variable can be stored by assigning it to a variable. In other words .pop( ) removes the last element of an array and returns that element. Any entry can be popped off; numbers, strings, nested arrays etc.

    var threeArr = [1, 4, 6];
    var oneDown = threeArr.pop( );
    console.log(oneDown); // Returns 6
    console.log(threeArr); // Returns [1, 4]

### .unshift( )

Shift allows you to remove the first item, unshift allows you to add an item to the start of the array. It works like push but rather adding to the end you are adding to the beginning.
var arr = [2, 3, 4];
arr.unshift(1);
// arr is now [1, 2, 3, 4]

## Shopping list

var myShoppingList = [[“Chicken, 1], [“Potato”, 6], [“Carrots”, 4]];

## Write reusable JS with Functions

In JS, we can divide up our code into reusable parts called functions. Here is an example:

    function functionName( ) {
    	console.log(“Hello World”);
    }

This function can then call or invoke this function by using its name followed by parentheses
functionName( );

Each time the function is called it will print the message, “Hello World”, on the dev console. All of the code between the curly braces will be executed every time the function is called.

    function reusableFunction( ) {
    	console.log(“Hi World”);
    }
    reusableFunction( )
    Hi World

## Passing Values to Functions with Arguments

Parameters are variables that act as placeholders for the values that are to be input to a function when it is called. When a function is defined, it is typically defined along with one or more parameters. The actual values that are input (or “passed”) into a function when it is called are known as arguments.

    function testFun(param1, param2)
    {
    	console.log(param1, param2);
    };

    testFun (“Hello ”, “World”);
    Hello World

Because we have passed two arguments “Hello” and “World”, Inside the function, param1 will = “Hello” and param2 = “World”. Note testFun can be called again with different arguments and the parameters would take on the value of the new arguments.

## Global Scope and Functions

In JS, scope refers to the visibility of variables. Variables which are defined outside of a function block have Global scope. This means, they ca nee seen everywhere in your JS code.

Variables which hare used without the var keyword are automatically created in the global scope. This runs the risk of creating unintended consequences elsewhere in your code or when running a function again. You should always declare variables with var.

    var myGlobal = 10; // This is a global variable as it is outside the function (local scope)

    function fun1( ) {
    	oopsGlobal = 5 // no var here so this gets assigned to the function below
    }

    function 2( ) {
    	var output = “”;
    	if (typeof oopsGlobal != “undefined”) {
    	output += “ oopsGlobal: ”;
    	}
    	console.log(output);
    }

## Local scope and functions

Variable which are declared within a function, as well as the function parameters have local scope. That means, they are only visible within that function.

    function myTest( ) {
    var loc =  “foo”;
    console.log(loc);
    }
    myTest( ); // logs “foo”
    console.log(loc); loc is not defined outside of the function and so cannot be identified

## Global vs. Local Scope in Functions

It is possible to have both local and globe variables with the same name. When you do this, the local variables takes precedence over the global variable.

    var someVar = “Hat”;
    function myFun( ) {
    	var someVar = “Head”;
    	Return someVar;
    }

The function “myFun” will return “Head” because the local version of the variable is present.

## Return a value from a function with Return

We can pass values into a function with arguments. You can use a return statement to send a value back out of a function.

    function plusThree(num) {
    	return num + 3;
    }
    var anser = plusThree(5); // 8

plusThree takes an argument for num and returns a value equal to num + 3.

## Understanding Undefined Value from a returned function

A function can include the return statement but it does not have to. In the case that the function doesn’t have a return statement, when you call it, the function processes the inner code but the return value is undefined.

    var sum = 0;
    function addSum(num) {
    	sum = sum + sum;
    }
    var returnedValue = addSum(3);

    // sum will be modified but the returned value is undefined

In the above exampled, addSum, is a function without a return statement. The function will change the global sum variable but the returned value of the function is undefined.

## Assignment with a returned value

Everything to the right of the assignment operator (=) is resolved before the value is assigned. This means we can take the return value of a function and assign it to a variable.

Assume we have a pre-defined a function, sum, which adds two numbers together, then:

    ourSum = sum(5, 12);

Will call sum function, which returns a value of 17 and assigns it to ourSum variable.

Example: Stand in Line

In CS a queue is an abstract Data Structure where items are kept in order. New items can be added at the back of the queue and old items are taken off from the front of the queue.

Write a function nextInLine which takes an array (arr) and a number (item) as arguments. Add the number to the end of the array, then remove the first element of the array.

the nextInLine function should then return the element that was removed.

    function nextInLine(arr, item) {
    	arr.push(item);
    	return arr.shift( );
    }

    var testArr = [1,2,3,4,5];
    console.log(nextInLine(testArr, 6)); // Returns [2,3,4,5,6]

## Understanding Boolean value

Booleans may only be one of two values, true or false. They are treated as on-off switches, where true is on and false if off. These two states are mutually exclusive. It is important to note that boolean values are never written in quotes.

## Use conditional logic with if statements

If statements are used to make decisions in code. The keyword if tells JS to executer the code in the curly brackets under certain conditions, defined in the parentheses. These conditions are known as Boolean conditions and they may only be true or false.

When the conditions evaluates to true, the program executes the statement inside the curly brackets. When the Boolean condition evaluates to false, the statement inside the curly braces will not execute. Example:

    function test (myCondition) {
    	if (myCondition) {
    		return “It was true”;
    	}
    	return “It was false”;
    }

    test(true); // returns “It was true”
    test(false); // returns “It was false”

When test is called with a value of true, the if statement evaluates myCondition to see if it is true or not. Since it is the true the function returns “It was true”. When we call test with a value of false, myCondition is not true and thus the other value is called.

## Comparison with the Equality operator

There are many comparison operators in a JS. All of these operators return boolean true or false values.

The most basic operator is the equality operator == this compares two values and returns true if they’re equivalent or false if they are not. This is different from the assignments operator, which assigns value at the right of the operator to a variable in the left.

    function equalityTest(myVal) {
    	if (myVal == 10) {
    		return “Equal”;
    	}
    	return “Not Equal”;
    }

If myVal is equal to 10 then the equality operator returns true, which means the code in the curly brackets will execute and the function will return “Equal”, if it is not true then it will return “Not Equal”.

In order for JS to compare two different data types e.g. numbers and strings, it must convert on type to another. This is known as Type Coercion, once it does, however, it can compare terms as follows:

    1 == 1 // true
    1 == 2 // false
    1 == “1” // true
    “3” == 3 // true

## Comparison with the strict equality operator

Strict equality, ===, is the counterpart to the equality operator. However, unlike the equality operator, which attempt to convert both values being compared to a common type, the strict equality operator does not perform a type conversion.

If the values being compared have different types, they are considered unequal and the strict equality operator will return false.

    3 === 3 // true
    3 === “3” // false

In JS, you can determine the type of a variable or a value with the typeof operator:

    typeof 3 // returns “number”
    typeof “3” // retunes “string”

## Comparisons with the Inequality operator

The inequality operator != is the opposite of the equality operator. It means “Not Equal” and returns false where equality would return true and vice versa. Like the equality operator, it can and willl convert data types of values while comparing:

    1 != 2 // true
    1 != “1” // false
    1 != ‘1’ // false
    1 != true // false
    0 != false // false

## Comparisons with the strict Inequality operator

The strict inequality operator !== is the logical opposite of the strict equality operator. It means “Strictly not equal” and returns false where strict equality would return true and vice versa. It will not convert data types.

    3 !== 3 // false
    3 !== ‘3’ // true
    4 !== 3 // false

## Comparisons with the Greater than operator

The greater than operator > compares the values of two numbers. If the number on the left is greater than the number to the right it returns true otherwise it returns false. Like the equality operator it too will convert data types while comparing

    5 > 3 // true
    7 > ‘3’ // true
    2 > 3 // false
    ‘1’ > 9 // false

## Comparisons with the Greater than or Equal to operator

The greater than or equal to operator >= compares the values of 2 numbers. If the number to the left is greater than or equal to the number on the right then it returns true, otherwise it returns false.

    6 >= 6 // true
    7 >= ‘3’ // true
    2 >= 3 // false
    ‘7’ >= 9 // false

## Comparisons with the Less than operator

The less than operator < compares the values of 2 numbers. If the number to the left is less than the number on the right then it returns true, otherwise it returns false. Like the equality operator it too will convert data types while comparing

    2 < 5 // true
    ‘3’ < 7 // true
    5 < 5 // false
    3 < 2 // false
    ‘8’ < 4 // false

## Comparisons with the Less than or Equal to operator

The less than or equal to operator <= compares the values of 2 numbers. If the number to the left is less than or equal to the number on the right then it returns true, otherwise it returns false.

    4 <= 5 // true
    ‘7’ <= 7 // true
    5 <= 5 // true
    3 <= 2 // false
    ‘8’ <= 4 // false

## Comparisons with the Logical And Operator

Sometimes you will need to test more than one thing at a time. The logical and operator (&&) returns true if and only if the operands to the left and right of it are ture.

The same effect could be achieved by nesting an if statement inside another if:

    if (num > 5) {
    	if (num < 10) {
    		return “Yes”;
    	}
    }
    return “No”;

This will only return yes if the num is greater than 5 and less than 10, the same logic can be written as:

    if (num > 5 && num < 10) {
    	return “Yes”;
    }
    return “No’;

## Comparisons with the Logical Or Operator

The logical or operator | | returns true if either of the operands is true, otherwise it returns false. The operator is composed of two pipe | symbols.

    if (num > 10) {
    	return “No”;
    }
    if (num < 5) {
    	return “No”;
    }
    return “Yes”

This will return “Yes” if a number is between 5 and 10 the same logic can be written as:

    if (num > 10 | | number < 5) {
    	return “No”;
    }
    return “Yes”;

## Introducing else statements

When a condition for an if statement is true, the block of code following it is executed. What about when the condition is false> Normally nothing would happen. With an else statement an alternate block of code can be executed:

    if (num > 10) {
    	return “Bigger than 10”;
    } else {
    	return “10 or less”;
    }

## Introducing Else If Statements

If you have multiple conditions that need to be addressed, you can chain if statements together with else if statements:

    if (num > 15) {
    	return “Bigger than 15”;
    } else if (num < 5) {
    	return “Smaller than 5”;
    } else {
    	return “Between 5 and 15”;
    }

## Logical Order in If Else statements

Order is important in if and else if statements. The function is executed from top to bottom so you will want to be careful of what statement comes first. For example:

    function foo(x) {
    if (x < 1) {
    	return “Less than one”;
    } else if (x < 2) {
    	return “Less than two”;
    } else {
    	return “Greater than or equal to two”;
    function foo(x) {
    	if (x < 2) {
    		return “Less than two”;
    	} else if (x < 1) {
    		return “Less than one”;
    	} else {
    		return “Greater than or equal to two”;
    	}
    }

While these two functions look nearly identical if we pass a number to both we get different outputs.
foo(0) // “Less than one”
bar(0) // “Less than two”

## Chaining If Else statements

if/else statements can be chained together for complex logic. Here is pseudocode of multiple chained if/else statements:

    if (condition) {
    	statement1
    } else if (condition2) {
    	statement2
    } else if (condition3) {
    	statement3
    . . .
    } else {
    	statementN
    }

Example: Golf Code

in the game of gold each hole has a par meaning the average number of strokes a golfer is expected to make in order to sink the ball in a hole to compel the play. Depending on how far above or below par your strokes are, there is a different nickname.

Your function will be passed par and strokes arguments. Return the correct string according to the this table which lists the strokes in order of priority; top (highest) to bottom (lowest):

    Strokes	Return
    1		“Hole-in-one!”
    <= par-2	“Eagle”
    par -1		“Birdie”
    par		“Par”
    par+1		“Bogey”
    par+2		“Double Bogey”
    >= par+3	“Go Home!”

    function golfScore(par, strokes) {
    	if (strokes === 1) {
    		return “Hole-in-one”
    	} else if (strokes <= par-2) {
    		return “Eagle”
    	} else if (strokes === par-1) {
    		return “Birdie”
    	} else if . . .
    	} else if (strokes >= par+3) {
    		return “Go Home!”
    	}

## Selecting from many Options with switch elements

If you have many options to choose from, use the switch statement. A switch statement tests a value and can have many case statements which define various possible values. Statements are executed from the first matched case value until a break is encountered. Here is a pseudocode example:

    switch(num) {
    	case value1:
    		statement1;
    		break;
    	case value2:
    		statement2;
    		break;
    . . .
    	case valueN:
    		statementN;
    		break;
    }

Case values are tested with strict equality = = = . The break tells JS to stop executing statements. If the break is emitted, the next statement will be executed. In a switch statement you may not be able to specify all possible values as case statements. Instead, you can add the default statement which will be executed if no matching case statements are found. Think of it like the final else statement in an if/else chain. A default statement should be the last case:

    switch(num) {
        case value1:
        statement1;
        break;
        case value2:
        statement2;
        break;
        . . .
        default:
        defaultStatement;
        break;
    }

## Multiple Identical Option in Switch Statements

If the break statement is omitted from a switch statement’s case, the following case statement(s) are executed until a break is encountered. IF you have multiple inputs with the same output, you can represent them in a switch statement like this:

    switch(val) {
    	case 1:
    	case 2:
    	case 3:
    		result = “1, 2, or 3”;
    	case 4:
    		result = “4 alone”;
    }

This means that cases for 1,2 and 3 will produce the same result.

## Replacing If Else chains with Switch

If you have many options to choose from, a switch statement can be easier to write than many chained if/else if statements. For example:

    if (val === 1) {
    	answer = “a”;
    } else if (val === 2) {
    	answer = “b”;
    } else {
    	answer = “c”;
    }

can be replaced with:

    switch(val) {
        case 1:
        answer = “a”;
        break;
        case 2:
        answer = “b”;
        break;
        default:
        answer = “c”;
    }

## Returning Boolean Values from Functions

You may recall from Comparison with the equality operator that all comparison operators return a boolean true or false value. Sometimes people use an if/else statement to do a comparison, like this:

    function isEqual(a, b) {
    	if (a === b) {
    		return true;
    	} else {
    		return false;
    	}
    }

But there is a better way to do this. Since = = = returns true or false, we can return the result of the comparison:

    function isEqual(a, b) {
    	return a === b;
    }

## Return Early pattern for functions

When a return statement is reached, the execution of the current function stops and control returns to the calling location:

    function myFun( ) {
    	console.log(“Hello”);
    	return “World”;
    	console.log(byebye)
    }
    myFun( );

The above outputs “Hello” to the console, returns “World, but “byebye” is never output, because the function exits at the return statement.

## Counting cards Task

You will write a card counting function. It will receive a card parameter, which can be a number or a string and increment or decrement the global count variable according to the card’s value (see table). The function will then return a string with the current count and the string Bet if the count is positive or Hold if the count is 0 or negative. The current count and the player’s decision (Bet or Hold) should be separated by a single space.

    Count Change	Cards
    +1			2, 3, 4, 5, 6
    0			7, 8, 9
    -1			10, ‘J’, ‘Q’, ‘K’, ‘A’

    var count = 0;

    function cc(card) {
    	var regex = /[JQKA]/;

    	if (card > 1 && card < 7) {
    		count++;
    	} else if (card === 10 | | String(card).match(regex) {
    		count - -;
    	}

    	if (count > 0) return count + “ Bet”;
    	return count + “ Hold”;
    }

## A note on regex https://regexr.com/

The RegExp constructor creates a regular expression object for matching text with a pattern. See favourites for more info.

## Build JavaScript Objects

Objects are similar to arrays, except that instead of using indexes to access and modify their data, you access the data in the objects through what are called properties.

Objects are useful for storing data in a structure way and can represent real world objects, like a cat. Here’s a sample cat object:

    var cat = {
        “name”: “Whiskers”,
        “legs”: 4,
        “tails”: 1,
        “enemies”: [“Water”, “Dogs”]
    };

In this example, all the properties are stored as strings e.g. “name” and “legs”. However, you can also use numbers as properties. You can even omit quotes for single-word string properties, as follows:

    var anotherObject = {
    	make: “Ford”,
    	5: “five”,
    	“model”: “focus”
    };

However, if your object has any non-string properties, Javascript will automatically typecast them as strings.

## Accessing Object Properties with Dot Notation

There are two ways to acmes the properties of an object: dot notation ( . ) and a bracket notation ( [ ] ), similar to an array.

Dot notation is what you use when you know the name of the property you’re trying to access ahead of time. Here is a sample of using door notation to draw an object’s property:

    var myObj = {
    	prop1: “val1”,
    	prop2: “val2”
    };
    var prop1val = myObj.prop1; // val1
    var prop2val = myObj.prop2; // val2

## Accessing Object Properties with Bracket Notation

The second way to access the properties of an object is bracket notation. Of the property of the object you are trying to access has a space in its name, you will need to use bracket notation. However,, you can still use bracket notation o object properties without spaces.

Here is a sample of using bracket notation to read an objects property:

    var myObj = {
    	“Space Name”: “Kirk”,
    	“More Space”: “Spock”,
    	“NoSpace” : “USS Enterprise”
    };
    myObj [“Space Name”]; // Kirk
    myObj [‘More Space’]; // Spock
    myObj[“NoSpace”]; // USS Enterprise

Property names with spaces must be in quotes, single or double.

## Accessing Object Properties with Variables

Another use of bracket notation on objects is to access a property which is stored as the value of a variable. This can be very useful for iterating through an objects properties or when accessing a lookup table.

Here is an example of using a variable to access a property:

    var dogs = {
    	Fido: “Mutt”, Hunter: “Doberman”, Snoopie: “Beagle”
    };
    var myDog = “Hunter”;
    var myBreed = dogs[myDog];
    console.log(myBreed); // “Doberman”

Another way you can use this concept is when the property’s name is collected dynamically during the program execution, as follows:

    var someObj = {
    	propName: “John”
    };
    function propPrefix(str) {
    	var s = “prop”;
    	return s + str;
    }
    var someProp = propPrefix (“Name”); // someProp now holds the value ‘propName’
    console.log(someObj[someProp]); // “John”

Note that we do not use quotes around the variable name when using it to access the property because we are using the value of the variable, not the name.

Using playerNumber variable to look up player 16 in testObj using bracket notation. Then assign that name to the player variable.

    var testObj = {
    	12: Namath”,
    	16: “Montana”,
    	19: “Unitas”
    };

    var playerNumber = 16;
    var player = testObj[playerNumber];

## Updating Object properties

After you’ve created a JavaScript object, you can update its properties at any time just like you would update any other variable. You can use either dot or bracket notation to update.

For example, let’s look at ourDog:

    var ourDog = {
    	“name”: “Camper”,
    	“legs”: 4,
    	“tails”: 1,
    	“friends”: [“everything!”]
    };

Camper is a very happy fog, let’s change his name to “Happy Camber”. This can be done by updating his object’s property name property:

    ourDog.name = “Happy Camper”; or
    ourDog[“name”] = “Happy Camper”;

Now when we evaluate ourDog.name, instead of “Camper” we will get “Happy Camper”.

## Add New properties to a JavaScript Object

You can add new properties to existing JavaScript objects the same way yo uwould modify the,.

Here’s how we would add a “bark” property ourDog:

    ourDog.bark = “bow-wow”;
    or
    ourDog[“bark”] = “bow-wow”;

Now when we evaluate ourDog.bark, we’ll get his bark, “bow-wow”.

## Delete Properties from a JS Object

We can also delete properties from objects like this:
delete ourDog.bark;

## Using Objects for Lookups

Objects can be thought of as a key/value storage, like a dictionary. IF you have tabular data, you can use an object to “lookup” value rather than a switch statement of an if/else chain. This is most useful when you know that your data is limited to a certain range. Here is an example of a simple reverse alphabet lookup:

    var alpha = {
      1:"Z",
      2:"Y",
      3:"X",
      4:"W",
      ...
      24:"C",
      25:"B",
      26:"A"
    };
    alpha[2]; // "Y"
    alpha[24]; // "C"

    var value = 2;
    alpha[value]; // “Y"

Create an object called lookup. Use it to look up val and assign the associated string to the result variable.

    function phoneticLookup(val) {
      var result = "";

    var lookup = {
        "alpha": "Adams",
        "bravo": "Boston",
        "charlie": "Chicago",
        "delta": "Denver",
        "echo": "Easy",
        "foxtrot": "Frank"
        };
        result = lookup[val];

        return result;
    }

    phoneticLookup("delta");

## Testing Objects for properties

Sometimes it’s useful to check if the property of a given object exists or not. We can use the .hasOwnProperty(propname) method of objects to determine if that object has the given property name. .hasOwnProperty( ) returns true or false if the property is found or not. For example:

    var myObj = {
    	top: “hat”,
    	bottom: “pants”
    };
    myObj.hasOwnProperty(“top”); / / true
    myObj.hasOWnProperty(“middle”); / / false

## Manipulating Complex Objects

Sometimes you may want to store data in a flexible Data Structure. A JS object is one way to handle flexible data. They allow for arbitrary combination of strings, numbers, booleans, arrays, functions and objects. Here is an example of a complex data structure:

    var ourMusic = [
    	{
    		“artist”: “Daft Punk”,
    		“title”: “Homework”,
    		“release_year”: 1997,
    		“formats”: [
    			“CD”,
    			“Cassette”,
    			“LP”
    		],
    		“gold”: true
    	}
    ];

This is an array which contains one object inside. The object has various pieces of metadata about an album. IT also has a nested “formats” array. If you want to add more albums, you can do this by adding records to the top level array.

Objects hold data in a property, which has a key-value format. In the example above, “artist”: “Daft Punk” is a property that has a key of “artist” and value of “Daft Punk”.

JavaScript Object Notation or JSON is a related data interchange format used to store data.

## Accessing Nested Objects

The sub-properties of objects can be accessed by chaining together the dot or bracket notation.

Here is a nested object:

    var ourStorage = {
    	“desk”: {
    		“drawer”: “stapler”
    	},
    	“cabinet”: {
    		“top drawer”: {
    			“folder1”: “a file”,
    			“folder2”: “secrets”
    			},
    			“bottom drawer”: “soda”
    		}
    	};
    	ourStorage.cabinet[“top drawer”].folder2; / / “secrets”
    	ourStorage.desk.drawer; / / “stapler”

## Accessing Nested Arrays

As we have seen in earlier examples, objects can contain both nested objects and nested arrays. Similar to accessing nested objects, Array bracket notation can be chained to access nested arrays.

Here is an example of how to access a nested array:

    var ourPets = [
    	{
    		animalType: “cat”,
    		names: [
    			“Meowzer”,
    			“Fluffy”,
    			“Kit-Cat”
    		]
    	},
    	{
    		animalType: “dog”,
    		names: [
    			“Spot”,
    			“Bowser”,
    			“Frankie”
    		]
    	}
    ];
    ourPets[0].names[1]; / / “Fluffy”
    ourPets[1].names[0]; / / “Spot”

Task: Record Collection

You are given a JSON object representing a part of your musical album collection. Each album has several properties and a unique id number as its key. Not all albums have complete information.

Write a function which takes an albums id (like 2548), a property prop (like “artist” or “tracks”}, and a value (like “Addicted to Love”) to modify the data in this collection.

if prop isn’t “tracks” and value isn’t empty (“ “), update or set the value for that record album’s property.

Your function must always return the entire collection object. There are several rules for handling incomplete data:

If prop is “tracks” but the album doesn’t have a “tracks” property, create an empty array before adding the new value to the album’s corresponding property.

if prop is “tracks” and value isn’t empty (“ “), push the value onto the end of the album’s exiting tracks array.

if value is empty (“ “), delete the given prop property from the album.

    var collection = {
      "2548": {
        album: "Slippery When Wet",
        artist: "Bon Jovi",
        tracks: ["Let It Rock", "You Give Love a Bad"]
      },
      "2468": {
        album: "1999",
        artist: "Prince",
        tracks: ["1999", "Little Red Corvette"]
      },
      "1245": {
        artist: "Robert Palmer",
        tracks: []
      },
      "5439": {
        album: "ABBA Gold"
      }
    };

    function updateRecords(id, prop, value) {
      if (prop === "tracks" && value !== "") {
        if (collection[id][prop]) {
          collection[id][prop].push(value);
        } else {
          collection[id][prop] = [value];
        }
      } else if (value !== "") {
        collection[id][prop] = value;
      } else {
        delete collection[id][prop];
      }

      return collection;
    }

**Redesigned code by Josh**

    // Setup
    var collection = {
        "2548": {
          "album": "Slippery When Wet",
          "artist": "Bon Jovi",
          "tracks": [
            "Let It Rock",
            "You Give Love a Bad Name"
          ]
        },
        "2468": {
          "album": "1999",
          "artist": "Prince",
          "tracks": [
            "1999",
            "Little Red Corvette"
          ]
        },
        "1245": {
          "artist": "Robert Palmer",
          "tracks": [ ]
        },
        "5439": {
          "album": "ABBA Gold"
        }
    };

    function updateRecords(id, prop, value) {
      var clone = Object.assign({}, collection)
      var album = clone[id]
      var currentProp = album[prop]

      if (prop === "tracks" && value !== "") {
        if (currentProp) {
          clone[id][prop].push(value);
        } else {
          clone[id][prop] = [value];
        }
      } else if (value !== "") {
        clone[id][prop] = value;
      } else {
        delete clone[id][prop];
      }

      var endValue = prop === 'tracks' ? [...album.tracks, value]

    updateRecords(5439, "artist", "ABBA");

## Iterate With JavaScript While Loops

You can run the same code multople times by using a loop.

The first type of loop we will learn is called a "while" loop because it runs "while" a specific condition is true and stops once that condition is no longer true.

    var ourArray = [];
    var i = 0
    while (i < 5) {
        ourArray.push(i);
        i++;
    }

## Iterate with JavaScript For Loops

You can run the same code multiple times by using a loop. The most common type of JS loop is called a "for loop" because it runs "for" a specific number of times.

For loops are declared with three optional expressions separated by semicolons:

    for ([initialization];[condition];[final-expression])

The initialization statement is executed one time only before the loop starts. It is typicsally used to define and setup your loop variable.

The condition statement is evaluated at the beginning of every loop iteration and will continue as long as it evaluates true. When condition is false at the start of the iteration, the loop will stop exectuing. This means if the condition starts as false, your loop will never execute.

The final-expression is executed at the end of each loop iteration, prior to the next condition cehck and is usually used to increment or decrement your loop counter.

In the following example we initialise with i = 0 and iterate while our condition is i < 5 is true. We'll increment i by 1 in each loop iteration with i++ as our final expression.

    var ourArray = [];
    for (var i = 0; i < 5; i++) {
        ourArray.push(i);
    }

    // our array will now contain (0, 1, 2, 3, 4).

## Iterate Odd Numbers With a For Loop

For loops dont have to iterate one at a time. By chsanging our final-expression, we can count by even numbers.

We'll start at i = 0 and loop while i < 10. We'll increment i by 2 each loop with i+=2

    var ourArray = [];
    for )var i = 0; i < 10; i+=2) {
        ourArray.push(i);
    }

    // our array will now contain (0, 2, 4, 6, 8,)

## Count Backwards With a For Loop

A for loop can also count backwards, so long as we can define the right conditions.

In order to count backwards by twos, we'll need to change our initialization, condition and final-expression.

We'll start at i = 10 and loop while i > 0. We'll decrement i by 2 each loop with i -= 2.

    var ourArray = [];
    for (var i=10; i > 0; i-=2) {
        ourArray.push(i);
    }

    // our array will now contain (10, 8, 6, 4, 2)

## Iterate Through an Array with a For Loop

A common task in JavaScript is to iterate through the contents of an array. One way to do that is with a for loop. This code will output each element of the array.

    var arr = [10, 9, 8, 7, 6];
    for (var i = 0; i < arr.length; i++) {
        console.log(arr[i]);
    }

Remember arrays have zer-based numbering, which means the last index of the array length is -1. Our condition for this loop is i < arr.length, which stops when i is at length -1.

## Nesting For Loops

If you have a multi-dimensional array, you can use the same logic as the prior waypoint to loop through both the array and any sub-arrays. Here is an example:

    var arr = [
            [1, 2], [3, 4], [5, 6]
        ];
        for (var i=0; i < arr.length; i++) {
            for (var j=0; j < arr[i].length; j++) {
                console.log(arr[i][j]);
            }
        }

This outputs each sub-element in arr one at a time. Note that for the inner loop, we are checking the .length of arr[i], since arr[i] is itself an array.

Challenge

Modify function multiplyAllso that it multiplies the productvariable by each number in the sub-arrays of arr

    function multiplyAll(arr) {
    var product = 1;
    for (var i = 0; i < arr.length; i++) {
        for (var x = 0; x < arr[i].length; x++) {
        product *= arr[i][x];
        }
    }
    return product;
    }

    multiplyAll([[1,2],[3,4],[5,6,7]]);

## Iterate with JavaScript Do...While Loops

You can run the same code multiple times by using a loop.

The next type of loop you will learn is called "do...while" loop because it first will "do" one pass of teh code inside the loop no matter what and then it runs "while" a specified condition is true and stops once that condition is no longer true.

    var ourArray = [];
    var i = 0;
    do {
        ourArray.push(i);
        i++;
    } while (i < 5);

This behaves just as you would expect with any other type of loop and the resulting array will look like [0, 1, 2, 3, 4]. However, what makes the do...while different from the other loops is how it behaves when the condition fails on the first check.

Here is a regular while loop that will run the code in the loop as long as i < 5.

    var ourArray = [];
    var i = 5;
    while (i < 5) {
        ourArray.push(i);
        i++;
    }

Notice that we initialise the value of i to be 5. When we execute the next line, we notice that i is not less thna 5. So we do not execute the code inside the loop. The result is that ourArray will end up with nothing added to it, so it will look like this [] when all the code in the example above finishes running.

Now, take a look ar a do...while loop.

    var ourArray = [];
    var i = 5;
    do {
        ourArray.push(i);
        i++;
    } while (i < 5);

In this case, we initialise the value i as 5, just like we did with the while loop. When we get to the next line, there is no check for the value i, so we go to the code inside the curly braces and execute it. We will add one element to the array and increment i before we get to the coniditon check. Then, when we get to checking if i < 5 see that i is now 6, which fails teh conditional check. So we exit the loop and are done. At teh end of the agove example the value of ourArray is [5].

Essentially, a do...while loop ensures that the code inside the loop will run at least once.

Let's try getting a do...while loop to work by pushing values to an array.

Change the while loop in the code to a do...while loop so that the loop will push the number 10 to myArray and i will be equal to 11 when your code finishes running:

    // Setup
    var myArray = [];
    var i = 10;

    // Only change code below this line.
    do {
        myArray.push(i);
    i++;
    } while (i < 5);

## Profile Lookup Challenge!

We have an array of object representing different people in our contacts list.

A lookUpProfile function that takes nam and a property (prop) as arguments has been pre-written for you.

The function should check if name is an actual contact's first name and the given property (prop) is a property of that contact.

If both are true, then return the "value" of that property.

If name does not correspond to any contacts then return "No such contact"

if prop does not correspond to any valid properties of a contact found to match name then return "No such property"

    var contacts = [
        {
            "firstName": "Akira",
            "lastName": "Laine",
            "number": "0543236543",
            "likes": ["Pizza", "Coding", "Brownie Points"]
        },
        {
            "firstName": "Harry",
            "lastName": "Potter",
            "number": "0994372684",
            "likes": ["Hogwarts", "Magic", "Hagrid"]
        },
        {
            "firstName": "Sherlock",
            "lastName": "Holmes",
            "number": "0487345643",
            "likes": ["Intriguing Cases", "Violin"]
        },
        {
            "firstName": "Kristian",
            "lastName": "Vos",
            "number": "unknown",
            "likes": ["JavaScript", "Gaming", "Foxes"]
        }
    ];


    function lookUpProfile(name, prop){
    for (var x = 0; x < contacts.length; x++) {
        if (contacts[x].firstName === name) {
            if (contacts[x].hasOwnProperty(prop)) {
                return contacts[x][prop];
            } else {
                return "No such property";
            }
        }
    }
    return "No such contact";
    }
    lookUpProfile("Akira", "likes");

This runs and "Akira" is matched to the "firstName" key in the first object, so the if statement returns true. "likes" is found within the first object, so the second if statement returns true. The value of "likes" is returns - "Pizza, "Coding", "Brownie Points".

The for loop runs, starting at the first object in the contacts list. If the firstName parameter passed into the function matches the value of the "firstName" key in the first object, the if statement passes. Then, we use .hasOwnProperty() method (checks if there’s a given property and returns a boolean) with prop as an argument. If it’s true, the value of prop is returned. If the second if statement fails, No such property is returned. If the first if statement fails, the for loop continues on to the next object in the contacts list. If the firstName parameter isn’t matched by the final contacts object, the for loop exits and No such contact is returned.

## Generate Random Fractions with JavaScript

Random numbers are useful for creating random behaviour. JavaScript has a Math.random() function that generates a random decimal number between 0 (inclusive) and not quite up to 1 (exclusive). Thus Math.random() can return 0 but never quite return 1.

Note
Like Storing Values with the Equal Operator, all function calls will be resolved before the return executes, so we can return the value of Math.random() function.

    function randomFraction() {
       return Math.random ();
    }

## Generate Random Whole Number with JavaScript

It's great that we can generate random decimal numbers, but it's even more useful if we use it to generate random whole numbers.

1. use Math.random() to generate a random decimal
2. Multiply that random decimal by 20
3. Use another function, Math.floor() to round the number down to its nearest whol number

Remember that Math.random() can never quite return a 1 and because we're rounding own, it's impossible to get 20. This technique will give us a whole number between 0 and 19.

Putting everything together, this is what out code looks like:

    Math.floor(Math.random() * 20);

## Generate Random Whole Numbers within a Range

Instead of generating a random number between zero and a given number like we did before, we can generate a random number that falls within a range of two specific numbers.

To do this, we'll define a minimum number min and a maximum number max.

Here's the formula we'll use. Take a moment to read it and try to understand what this code is doing:

    Math.floor(Math.random() * (max - min + 1)) + min

## Use the parseInt Function

The parseInt() function parses a string and returns an integer. Here's an example:

    var a = parseInt("007");

The above function converts the string "007" into the integer 7. If the first character in the string can't be converted into a number then it returns NaN.

## Use the parseInt Function with a Radix

The parseInt() function pasrses a string and returns an integer. It takes a second argument for the radix, which specifies the base of the number in the string. The radix can be an integer between 2 and 36.

The function call looks like:

    parseInt(string, radix);

An example:

    var a = parseInt("11", 2);

The radix variable says that "11" is in the binary system, or base 2. This examples converts the string "11" into an integer 3.

## Use the Conditional (Ternary) Operator

The conditional operator, also called the ternary operator, can be used as a one line if-else expression. The syntax is:

    condition ? statement-if-true : statement-if-false;

The following fucntion uses an if-else statement to check a condition:

    function findGreater(a, b) {
        if(a > b) {
            return "a is greater";
        } else {
            return "b is greater";
        }
    }

This can be re-written using the conditional operator:

    function findGreater(a, b) {
        return a > b ? "a is greater" : "b is greater";
    }

## Use Multiple Conditional (Ternary) Operators

In the previous challenge, you used a single conditional operator. You can also chain them otgether to check for multiple conditions.

The following function use if, else if and else statements to check multiple conditions:

    function findGreaterOrEqual(a, b) {
        if (a === b) {
            return "a and b are equal";
        } else if (a > b) {
            return "a is greater";
        } else {
            return "b is greater";
        }
    }

This can be re-written with multiple conditional operators:

    function findGreaterOrEqual(a, b) {
        return (a === b) ? "a and b are equal" : (a > b) ? "a is greater" : "b is greater";
    }

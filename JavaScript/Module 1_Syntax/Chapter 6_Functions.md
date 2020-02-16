# Chapter 6: Functions

[intro-to-javascript](https://cn.udacity.com/course/intro-to-javascript--ud803) ([backup](https://classroom.udacity.com/courses/ud803))

- Topic 1. Declaring & Running Functions
- Topic 2. Return Values of Functions
- Topic 3.  Scope
- Topic 4. Hoisting
- Topic 5. Function Expressions

---

# Topic 1. Declaring & Running Functions
## How to _declare_ a function

**Functions**  allow you to package up lines of code that you can use (and often reuse) in your programs.

Sometimes they take  **parameters**  like the pizza button from the beginning of this lesson.  `reheatPizza()`  had one parameter: the number of slices.

```
function reheatPizza(numSlices) {
  // code that figures out reheat settings!
}
```

The  `reverseString()`  function that you saw also had one parameter: the string to be reversed.

```
function reverseString(reverseMe) {
  // code to reverse a string!
}
```

In both cases, the parameter is listed as a variable after the function name, inside the parentheses. And, if there were multiple parameters, you would just separate them with commas.

```
function doubleGreeting(name, otherName) {
  // code to greet two people!
}
```

But, you can also have functions that don't have any parameters. Instead, they just package up some code and perform some task. In this case, you would just leave the parentheses empty. Take this one for example. Here's a simple function that just prints out  `"Hello!"`.

```
// accepts no parameters! parentheses are empty
function sayHello() {
  var message = "Hello!"
  console.log(message);
}
```

If you tried pasting any of the functions above into the JavaScript console, you probably didn't notice much happen. In fact, you probably saw `undefined` returned back to you. `undefined` is the default return value on the console when nothing is _explicitly_ returned using the special `return` keyword.

### Return statements

In the  `sayHello()`  function above, a value is  **printed**  to the console with  `console.log`, but not explicitly returned with a  **return statement**. You can write a return statement by using the  `return`  keyword followed by the expression or value that you want to return.

```
// declares the sayHello function
function sayHello() {
  var message = "Hello!"
  return message; // returns value instead of printing it
}
```

## How to  _run_  a function

Now, to get your function to  _do something_, you have to  **invoke**  or  **call**  the function using the function name, followed by parentheses with any  **arguments**  that are passed into it. Functions are like machines. You can build the machine, but it won't do anything unless you also turn it on. Here's how you would call the  `sayHello()`  function from before, and then use the return value to print to the console:

```
// declares the sayHello function
function sayHello() {
  var message = "Hello!"
  return message; // returns value instead of printing it
}

// function returns "Hello!" and console.log prints the return value
console.log(sayHello());
```

> **Prints:**  "Hello!"

## Parameters vs. Arguments

At first, it can be a bit tricky to know when something is either a parameter or an argument. The key difference is in where they show up in the code. A  **parameter**  is always going to be a  _variable_  name and appears in the function declaration. On the other hand, an  **argument**  is always going to be a  _value_  (i.e. any of the JavaScript data types - a number, a string, a boolean, etc.) and will always appear in the code when the function is called or invoked.

## *Summary*

- **Functions**  package up code so you can easily use (and reuse) a block of code.  
- **Parameters**  are variables that are used to store the data that's passed into a function for the function to use.  
- **Arguments**  are the actual data that's passed into a function when it is invoked.

	```
	// x and y are parameters in this function declaration
	function add(x, y) {
	  // function body
	  var sum = x + y;
	  return sum; // return statement
	}

	// 1 and 2 are passed into the function as arguments
	var sum = add(1, 2);
	```

- The  **Function Body**  is enclosed inside curly brackets:

	```
	function add(x, y) {
	  // function body!
	}
	```

- **Return Statements**  explicitly make your function return a value:

	```
	return sum;
	```

- You  **Invoke**  or  **Call**  a function to have it do something:

	```
	add(1, 2);
	```

	> **Returns:**  3

## *Exercise*
### Directions

Write a function called  `laugh()`  that takes one parameter,  `num`  that represents the number of  `"ha"`s to return.

> **TIP:**  You might need a loop to solve this!

Here's an example of the output and how to call the function that you will write:

```
console.log(laugh(3));
```

> **Prints:**  "hahaha!"

### Code
```
/*
 * Programming Quiz: Laugh it Off 2 (5-2)
 *
 * Write a function called `laugh` with a parameter named `num` that represents the number of "ha"s to return.
 *
 * Note:
 *  - make sure your the final character is an exclamation mark ("!")
 *  - make sure that your function produces the correct results when it is called multiple times
 */
function laugh(num){
    var laughSound = "";
    for(var i = 0; i < num; i++){
        laughSound += "ha";
    }
    laughSound = laughSound+"!";
    return laughSound;
}
console.log(laugh(3));
```

# Topic 2. Return Values of Functions
## Return V.S. Print
It’s important to understand that  **return**  and  **print**  are not the same thing. Printing a value to the JavaScript console only displays a value (that you can view for debugging purposes), but the value it displays can't really be used for anything more than that. For this reason, you should remember to only use  `console.log`  to test your code in the JavaScript console.

Paste the following function declaration  _and_  function invocation into the JavaScript console to see the difference between logging (printing) and returning:

```
function isThisWorking(input) {
  console.log("Printing: isThisWorking was called and " + input + " was passed in as an argument.");
  return "Returning: I am returning this string!";
}

isThisWorking(3);
```

> **Prints:**  "Printing: isThisWorking was called and 3 was passed in as an argument"  
> **Returns:**  "Returning: I am returning this string!"

If you don't explicitly define a return value, the function will return  `undefined`  by default.

```
function isThisWorking(input) {
  console.log("Printing: isThisWorking was called and " + input + " was passed in as an argument.");
}

isThisWorking(3);
```

> **Prints:**  "Printing: isThisWorking was called and 3 was passed in as an argument"  
> **Returns:**  undefined

## Using Return Values
Returning a value from a function is great, but what's the use of a return value if you're not going to use the value to do something?

_A function's return value can be stored in a variable or reused throughout your program as a function argument_. Here, we have a function that adds two numbers together, and another function that divides a number by 2. We can find the average of 5 and 7 by using the  `add()`  function to add a pair of numbers together, and then by passing the sum of the two numbers  `add(5, 7)`  into the function  `divideByTwo()`  as an argument.

And finally, we can even store the final answer in a variable called  `average`  and use the variable to perform even more calculations in more places!
```
// returns the sum of two numbers
function add(x, y) {
  return x + y;
}


// returns the value of a number divided by 2
function divideByTwo(num) {
  return num / 2;
}


var sum = add(5, 7); // call the "add" function and store the returned value in the "sum" variable
var average = divideByTwo(sum); // call the "divideByTwo" function and store the returned value in the "average" variable
```
# Topic 3.  Scope
## Global Scope & Function Scope

- **Global Scope**

	> Identifiers can be accessed everywhere within your program.

	If you define an identifier outside of all of your functions, it is considered part of the global scope. 
	All functions n your program can access variables in global scope.

	**Global Variables**
	So you might be wondering:

	> "Why wouldn't I always use global variables? Then, I would never need to use function arguments since ALL my functions would have access to EVERYTHING!"

	Well... Global variables might seem like a convenient idea at first, especially when you're writing small scripts and programs, but there are many reasons why you shouldn't use them unless you have to. For instance, global variables can conflict with other global variables of the same name. Once your programs get larger and larger, it'll get harder and harder to keep track and prevent this from happening.

	There are also other reasons you'll learn more about in more advanced courses. But for now, just work on minimizing the use of global variables as much as possible.

- **Function Scope**

	> Identifiers can be accessed everywhere inside the function it was defined in. 

	If you define an identifier inside of a function, it will be visible everywhere inside that function even inside other functions inside that function.

## Shadowing (Overriding)

### QUESTION 1 OF 2

- **Question**

	Without pasting into your console, what do you think this code will print out?

	```
	var x = 1;

	function addTwo() {
	  x = x + 2;
	}

	addTwo();
	x = x + 1;
	console.log(x);
	```

- **Answer**
	>  4
    
- **Notes**
	The global variable `x` is assigned the value of 1.  
	Then, the function `addTwo()` increments the variable by 2.  
	Next, the variable is incremented by 1.  
	Finally, it's printed out using `console.log`.

### QUESTION 2 OF 2

- **Question**
	Without pasting into your console, what do you think this code will print out?

	```
	var x = 1;

	function addTwo() {
	  var x = x + 2;
	}

	addTwo();
	x = x + 1;
	console.log(x);
	```

- **Answer**
	> 2

- **Notes**
	The global variable  `x`  is incremented by 1. Since the global variable's original value was 1, and it was incremented by 1,  `console.log`  will print out 2.

	The variable assignment inside the function  `addTwo()`  only has function scope, so its affect is not reflected outside the function.

## *Summary*

-   If an identifier is declared in  **global scope**, it's available  _everywhere_.
-   If an identifier is declared in  **function scope**, it's available  _in the function_  it was declared in (even in functions declared inside the function).
-   When trying to access an identifier, the JavaScript Engine will first look in the current function. If it doesn't find anything, it will continue to the next outer function to see if it can find the identifier there. It will keep doing this until it reaches the global scope.
-   Global identifiers are a bad idea. They can lead to bad variable names, conflicting variable names, and messy code.

# Topic 4. Hoisting

Sometimes your JavaScript code will produce errors that may seem counterintuitive at first.  **Hoisting**  is another one of those topics that might be the cause of some of these tricky errors you're debugging.

## Hoisting for Function Declarations
In most programming languages, you have to declare a function before you can call it. Basically the idea is that code's read from top to bottom, so there's no way that we should be able to call the function if it hasn't even been declared yet.

Actually it **works** in JavaScript.

> Before any JavaScript is executed, all function declarations are **"hoisted"** to the top of their current scope.

## Hoisting for Variable Declarations

The **variable declaration** is hoisted,  not the **variable assignment**.

```
var greeting = "Hello";
//variable declaration & assignment in the same line
```
Above code is equal to...
```
var greeting; //variable declaration
greeting = "Hello"; //variable assignment
```

## *Exercise*

### QUESTION 1 OF 3

- **Question**

	What value will be printed to the console?

	```
	sayHi("Julia");

	function sayHi(name) {
	  console.log(greeting + " " + name);
	  var greeting;
	}
	```

- **Answer**
    
	>  undefined Julia

 - **Notes**
	The function declaration is hoisted to the top of its current scope, and inside the function, the `greeting` variable declaration is also hoisted to the top of its function scope.   

### QUESTION 2 OF 3

- **Question**

	What value will be printed to the console?

	```
	sayHi("Julia");

	function sayHi(name) {
	  console.log(greeting + " " + name);
	  var greeting = "Hello";
	}

	```

- **Answer**
	>   undefined Julia

- **Notes**
		The variable  _declaration_  is hoisted to the top of current scope (the top of the function). Remember that the  _declaration_  is hoisted,  _not_  the  _assignment_. The code inside  `sayHi`  is equivalent to:

	```
	var greeting;
	console.log(greeting + " " + name);
	greeting = "Hello";
	```
    
### QUESTION 3 OF 3

- **Question**

	What value will be printed to the console?

	```
	function sayHi(name) {
	  var greeting = "Hello";
	  console.log(greeting + " " + name);
	}

	sayHi("Julia");
	```

- **Answer**
	> Hello Julia

- **Notes**
	Not many surprises here! The variable declaration _and_ assignment are both already at the top of the function scope, so the function will print out: "Hello Julia"


## *Summary*

-   JavaScript hoists function declarations and variable declarations to the top of the current scope.
-   Variable  _assignments_  are not hoisted.
-   Declare functions and variables at the top of your scripts, so the syntax and behavior are consistent with each other.

# Exercise: Build a Triangle

## Directions

For this quiz, you're going to create a function called  `buildTriangle()`  that will accept an input (the triangle at its widest width) and will return the string representation of a triangle. See the example output below.

```
buildTriangle(10);
```

**Returns**:
```
* 
* * 
* * * 
* * * * 
* * * * * 
* * * * * * 
* * * * * * * 
* * * * * * * * 
* * * * * * * * * 
* * * * * * * * * * 
```
## Code
```
/*
 * Programming Quiz: Build A Triangle (5-3)
 */

// creates a line of * for a given length
function makeLine(length) {
    var line = "";
    for (var j = 1; j <= length; j++) {
        line += "* ";
    }
    return line + "\n";
}

// your code goes here.  Make sure you call makeLine() in your own code.
function buildTriangle(rowCount) {
    var triangle = ""
    for (var j = 1; j <= rowCount; j++) {
        triangle += makeLine(j);
    }
    return triangle;
}

// test your code by uncommenting the following line
console.log(buildTriangle(10));
```

# Topic 5. Function Expressions

## Function Expressions
Once you know how to declare a function, a whole new set of possibilities will open up to you.

For instance, remember how you can store anything you want in a variable? Well, in JavaScript, you can also store functions in variables. When a function is stored  _inside_  a variable it's called a  **function expression**.

### Anonymous Function Expressions
```
//anonymous function expressions
var catSays = function(max) {
  var catMessage = "";
  for (var i = 0; i < max; i++) {
    catMessage += "meow ";
  }
  return catMessage;
};
//call the function
catSays(3);
```

Notice how the  `function`  keyword no longer has a name.

```
//anonymous function expressions
var catSays = function(max) { 
  // code here 
};
```

It's an  **anonymous function**, a function with no name, and you've stored it in a variable called  `catSays`.

And, if you try accessing the value of the variable  `catSays`, you'll even see the function returned back to you.

```
catSays;
```

> **Returns:**  an **anonymous function**
> 
> ```
> function(max) {
>   var catMessage = ""
>   for (var i = 0; i < max; i++) {
>     catMessage += "meow ";
>   }
>   return catMessage;
> }
> ```

### Named Function Expressions
[video]
```
//named function expressions
var catSays = function displayCatSays(max) {
  var catMessage = "";
  for (var i = 0; i < max; i++) {
    catMessage += "meow ";
  }
  return catMessage;
};

//call the function
//calling the function is not different than before
//use the variable name, not the function's name to call it, or else you will get a reference error
catSays(3);
```

## Function Expressions & Hoisting

Deciding when to use a function expression and when to use a function declaration can depend on a few things, and you will see some ways to use them in the next section. But, one thing you'll want to be careful of, is hoisting.

All  _function declarations are hoisted_  and loaded before the script is actually run.  _Function expressions are not hoisted_, since they involve variable assignment, and only variable declarations are hoisted. The function expression will not be loaded until the interpreter reaches it in the script.

## Patterns with Function Expressions
### Phase 1: Functions as Parameters
Being able to store a function in a variable makes it really simple to pass the function into another function. A function that is passed into another function is called a **callback**. Let's say you had a `helloCat()` function, and you wanted it to return "Hello" followed by a string of "meows" like you had with `catSays`. Well, rather than redoing all of your hard work, you can make `helloCat()` accept a callback function, and pass in `catSays`.

```
// function expression catSays
var catSays = function(max) {
  var catMessage = "";
  for (var i = 0; i < max; i++) {
    catMessage += "meow ";
  }
  return catMessage;
};

// function declaration helloCat accepting a callback
function helloCat(callbackFunc) {
  return "Hello " + callbackFunc(3);
}

// pass in catSays as a callback function
helloCat(catSays);
```

### Phase 2: Inline Function Expressions
#### Named Inline Function Expressions
A function expression is when a function is assigned to a variable. And, in JavaScript, this can also happen when you pass a function  _inline_  as an argument to another function. Take the  `favoriteMovie`  example for instance:

- **Before:** Not Inline
	```
	// Function expression that assigns the function displayFavorite 
	// to the variable favoriteMovie
	var favoriteMovie = function displayFavorite(movieName) {
	  console.log("My favorite movie is " + movieName);
	};

	// Function declaration that has two parameters: a function for displaying
	// a message, along with a name of a movie
	function movies(messageFunction, name) {
	  messageFunction(name);
	}

	// Call the movies function, pass in the favoriteMovie function and name of movie
	movies(favoriteMovie, "Finding Nemo");
	```
	→ using anonymous function: see next session

	> **Returns:**  My favorite movie is Finding Nemo


But you could have bypassed the first assignment of the function, by passing the function to the  `movies()`  function inline.

- **After:** Inline
	```
	// Function declaration that takes in two arguments: a function for displaying
	// a message, along with a name of a movie
	function movies(messageFunction, name) {
	  messageFunction(name);
	}

	// Call the movies function, pass in the function and name of movie
	movies(function displayFavorite(movieName) {
	  console.log("My favorite movie is " + movieName);
	}, "Finding Nemo");
	```
	→ using anonymous function: see next session

	> **Returns:**  My favorite movie is Finding Nemo

This type of syntax, writing function expressions that pass a function into another function inline, is really common in JavaScript. It can be a little tricky at first, but be patient, keep practicing, and you'll start to get the hang of it!

### Phase 3: Anonymous Inline Function Expressions
With the same example mentioned above...
- **Before:** Not Inline
	above example → using anonymous function:
	```
	// Function expression that assigns the function displayFavorite 
	// to the variable favoriteMovie
	var favoriteMovie = function(movieName) {
	  console.log("My favorite movie is " + movieName);
	};

	// Function declaration that has two parameters: a function for displaying
	// a message, along with a name of a movie
	function movies(messageFunction, name) {
	  messageFunction(name);
	}

	// Call the movies function, pass in the favoriteMovie function and name of movie
	movies(favoriteMovie, "Finding Nemo");
	```
	> **Returns:**  My favorite movie is Finding Nemo
	
- **After:** Inline
	above example → using anonymous function:
	```
	// Function declaration that takes in two arguments: a function for displaying
	// a message, along with a name of a movie
	function movies(messageFunction, name) {
	  messageFunction(name);
	}

	// Call the movies function, pass in the function and name of movie
	movies(function(movieName) {
	  console.log("My favorite movie is " + movieName);
	}, "Finding Nemo");
	```
	> **Returns:**  My favorite movie is Finding Nemo

## Why use anonymous inline function expressions?

Using an anonymous inline function expression might seem like a very not-useful thing at first. Why define a function that can only be used once and you can't even call it by name?

Anonymous inline function expressions are often used with function callbacks that are probably not going to be reused elsewhere. Yes, you could store the function in a variable, give it a name, and pass it in like you saw in the examples above. However, when you know the function is not going to be reused, it could save you many lines of code to just define it inline.

## *Summary*
**Function Expression**: When a function is assigned to a variable. The function can be named, or anonymous. Use the variable name to call a function defined in a function expression.

```
// anonymous function expression
var doSomething = function(y) {
  return y + 1;
};
```

```
// named function expression
var doSomething = function addOne(y) {
  return y + 1;
};
```

```
// for either of the definitions above, call the function like this:
doSomething(5);
```

> **Returns:**  6

You can even pass a function into another function  _inline_. This pattern is commonly used in JavaScript, and can be helpful streamlining your code.

```
// function declaration that takes in two arguments: a function for displaying
// a message, along with a name of a movie
function movies(messageFunction, name) {
  messageFunction(name);
}

// call the movies function, pass in the function and name of movie
movies(function displayFavorite(movieName) {
  console.log("My favorite movie is " + movieName);
}, "Finding Nemo");
```
→ using anonymous function:
```
// function declaration that takes in two arguments: a function for displaying
// a message, along with a name of a movie
function movies(messageFunction, name) {
  messageFunction(name);
}

// call the movies function, pass in the function and name of movie
movies(function(movieName) {
  console.log("My favorite movie is " + movieName);
}, "Finding Nemo");
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM5Mjc4ODIwNl19
-->
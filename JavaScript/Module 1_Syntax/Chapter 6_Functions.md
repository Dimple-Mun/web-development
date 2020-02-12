- Declaring & Running Functions

# Declaring & Running Functions
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

# _Recap_
## What you've learned so far:

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

# *Exercise*
## Directions

Write a function called  `laugh()`  that takes one parameter,  `num`  that represents the number of  `"ha"`s to return.

> **TIP:**  You might need a loop to solve this!

Here's an example of the output and how to call the function that you will write:

```
console.log(laugh(3));
```

> **Prints:**  "hahaha!"

## Code
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

# Return Values of Functions
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

# Using Return Values
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
# Scope
## Global Scope
Identifiers can be accessed everywhere within your program.

If you define an identifier outside of all of your functions, it is considered part of the global scope. 
## Functional Scope
Identifiers can be accessed everywhere inside the function it was defined in. 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMDk0NjkzNThdfQ==
-->
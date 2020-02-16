# Chapter 2: Function Updates in ES6

Functions are one of the primary data structures in JavaScript; they've been around  _forever_.

## Topic 1: Arrow Functions

ES6 introduces a new kind of function called the  **arrow function**. Arrow functions are very similar to regular functions in behavior, but are quite different syntactically. The following code takes a list of names and converts each one to uppercase using a regular function:

```
const upperizedNames = ['Farrin', 'Kagure', 'Asser'].map(function(name) { 
  return name.toUpperCase();
});
```

The code below does the same thing  _except_  instead of passing a regular function to the  `map()`  method, it passes an arrow function. Notice the  _arrow_  in the arrow function (  `=>`  ) in the code below:

```
const upperizedNames = ['Farrin', 'Kagure', 'Asser'].map(
  name => name.toUpperCase()
);
```

The only change to the code above is the code inside the  `map()`  method. It takes a regular function and changes it to use an arrow function.

> **NOTE:**  Not sure how  `map()`  works? It's a method on the Array prototype. You pass a function to it, and it calls that function once on every element in the array. It then gathers the returned values from each function call and makes a new array with those results. For more info, check out  [MDN's documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map).

### Convert a function to an arrow function
#### Example 1
```
const upperizedNames = ['Farrin', 'Kagure', 'Asser'].map(function(name) { 
  return name.toUpperCase();
});
```

With the function above, there are only a few steps for converting the existing "normal" function into an arrow function.

-   remove the  `function`  keyword
-   remove the parentheses`()`
-   remove the opening and closing curly braces`{ }`
-   remove the  `return`  keyword
-   remove the semicolon`;`
-   add an arrow (  `=>`  ) between the parameter list and the function body

=> Arrow Function

```
const upperizedNames = ['Farrin', 'Kagure', 'Asser'].map(name => name.toUpperCase());
```

#### Example 2
```
const names = ['Afghanistan', 'Aruba', 'Bahamas', 'Chile', 'Fiji', 'Gabon', 'Luxembourg', 'Nepal', 'Singapore', 'Uganda', 'Zimbabwe'];

const longNames = names.filter(function(name) {
  return name.length > 6;
});
```
=> Arrow Function
```
const names = ['Afghanistan', 'Aruba', 'Bahamas', 'Chile', 'Fiji', 'Gabon', 'Luxembourg', 'Nepal', 'Singapore', 'Uganda', 'Zimbabwe'];

const longNames = names.filter(name => name.length > 6);
```

### Using Arrow Functions
Regular functions can be either  **function declarations**  or  **function expressions**, however arrow functions are  _always_  **expressions**. In fact, their full name is "arrow function expressions", so they can only be used where an expression is valid. This includes being:

-   stored in a variable,
-   passed as an argument to a function,
-   and stored in an object's property.

One confusing syntax is when an arrow function is stored in a variable.

```
const greet = name => `Hello ${name}!`;
```

In the code above, the arrow function is stored in the  `greet`  variable and you'd call it like this:

```
greet('Asser');
```

> **Returns:**  Hello Asser!

#### Parentheses and arrow function parameters

You might have noticed the arrow function from the  `greet()`  function looks like this:

```
name => `Hello ${name}!` 
```

If you recall, the parameter list appears before the arrow function's arrow (i.e.  `=>`). If there's only  **one**  parameter in the list, then you can write it just like the example above. But, if there are  **two or more**  items in the parameter list, or if there are  **zero**  items in the list, then you need to wrap the list in parentheses:

```
// empty parameter list requires parentheses
const sayHi = () => console.log('Hello Udacity Student!');
sayHi();
```

> **Prints:**  Hello Udacity Student!

```
// multiple parameters requires parentheses
const orderIceCream = (flavor, cone) => console.log(`Here's your ${flavor} ice cream in a ${cone} cone.`);
orderIceCream('chocolate', 'waffle');
```

> **Prints:**  Here's your chocolate ice cream in a waffle cone

### Question

**Questions:** 

Which of the following choices have correctly formatted arrow functions?

**Answers:** 
-   setTimeout(() => {  
    console.log('starting the test');  
    test.start();  
    }, 2000);
    
-   setTimeout( _ => {  
    console.log('starting the test');  
    test.start();  
    }, 2000);
    
-   const vowels = 'aeiou'.split('');  
    const bigVowels = vowels.map( (letter) => letter.toUpperCase() );
    
-   const vowels = 'aeiou'.split('');  
    const bigVowels = vowels.map( letter => letter.toUpperCase() );

**Notes:** 
> Actually, each one of these is correct. If there's no parameter to the function, you just use a pair of empty parentheses like option 1. Alternatively, some developers choose to use an underscore as their single parameter. The underscore never gets used, so it's  `undefined`  inside the function, but it's a common technique.
> The only difference between options 3 and 4 is the use of the parentheses around  `letter`. Typically, if there's only one parameter, then no parentheses are used, but it's not wrong.

So arrow functions are awesome!

-   The syntax is a lot shorter,
-   it's easier to write and read short, single-line functions,
-   and they automatically return when using the concise body syntax!

> **WARNING:**  Everything's not all ponies and rainbows though, and there are definitely times when you might  _not_  want to use an arrow function. So before you wipe from your memory how to write a traditional function, check out these implications:
> 
> -   there's a gotcha with the  `this`  keyword in arrow functions
>     -   go to the next lesson to find out the details!
> -   arrow functions are only  _expressions_
>     -   there's no such thing as an arrow function declaration



<!--stackedit_data:
eyJoaXN0b3J5IjpbMzA0NjQ2ODRdfQ==
-->
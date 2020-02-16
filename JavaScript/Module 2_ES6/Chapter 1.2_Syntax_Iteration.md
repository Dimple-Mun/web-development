# Chapter 1: Syntax Updates in ES6
## ❤*Chapter 1.2: Iteration*❤

> Iteration is a new mechanism for looping through data in ES6.

## Topic 1: Introduction to Iteration

### What is iteration

**迭代**（iteration）：重复反馈过程的活动，每一次迭代的结果会作为下一次迭代的初始值。（A重复调用B）

迭代是一个**环结构**，从初始状态开始，每次迭代都遍历这个环，并更新状态，多次迭代直到到达结束状态。

### What's New in ES6

-   iterable protocol
    
    > allows JavaScript objects to define or customize their **iteration behavior**
    
-   for...of loop
    
    > a loop that iterates over iterable objects
    
    The **for...of loop** is the most recent addition to the family of for loops in JavaScript.
    
    It combines the strengths of its siblings, the **for loop** and the **for...in loop**, to loop over any type of data that is **iterable** (meaning it follows the [iterable protocol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) which we'll look at in lesson 3). By default, this includes the data types String, Array, Map, and Set—notably absent from this list is the `Object` data type (i.e. `{}`). Objects are not iterable, by default.
    

## Topic 2: Family of For Loops

### The for loop

The **for loop** is obviously the most common type of loop there is, so this should be a quick refresher.

```
const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (let i = 0; i < digits.length; i++) {
  console.log(digits[i]);
}

```

> **Prints:**  
> 0  
> 1  
> 2  
> 3  
> 4  
> 5  
> 6  
> 7  
> 8  
> 9

Really the biggest downside of a for loop is having to keep track of **the counter** and **exit condition**.

In this example, we’re using the variable `I` as a counter to keep track of the loop and to access values in the array. We’re also using `digits.length` to determine the exit condition for the loop. If you just glance at this code, it can sometimes be confusing exactly what’s happening; especially for beginners.

While **for loops** certainly have an advantage when looping through arrays, some data is not structured like an array, so a for loop isn’t always an option.

### The for...in loop

The **for...in loop** improves upon the weaknesses of the **for loop** by eliminating the **counting logic** and **exit condition**.

```
const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (const index in digits) {
  console.log(digits[index]);
}

```

> **Prints:**  
> 0  
> 1  
> 2  
> 3  
> 4  
> 5  
> 6  
> 7  
> 8  
> 9

But, you still have to deal with the issue of using an index to access the values of the array, and that stinks; it almost makes it more confusing than before.

Also, the **for...in loop** can get you into big trouble when you need to add an extra method to an array (or another object). Because **for...in loops** loop over all enumerable properties, this means if you add any additional properties to the array's prototype, then those properties will also appear in the loop.

```
Array.prototype.decimalfy = function() {
  for (let i = 0; i < this.length; i++) {
    this[i] = this[i].toFixed(2);
  }
};

const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (const index in digits) {
  console.log(digits[index]);
}

```

> **Prints:**  
> 0  
> 1  
> 2  
> 3  
> 4  
> 5  
> 6  
> 7  
> 8  
> 9  
> function() {  
>  for (let i = 0; i < this.length; i++) {  
>   this[i] = this[i].toFixed(2);  
>  }  
> }

Gross! This is why **for...in loops** are discouraged when looping over arrays.

> **NOTE:** The forEach loop is another type of for loop in JavaScript. However, forEach() is actually an array method, so it can only be used exclusively with arrays. There is also no way to stop or break a forEach loop. If you need that type of behavior in your loop, you’ll have to use a basic for loop.

### The for...of loop

The **for...of loop** is used to loop over any type of data that is iterable.

You write a **for...of loop** almost exactly like you would write a **for...in loop**, except you swap out `in` with `of` and you can drop the **index**.

```
const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (const digit of digits) {
  console.log(digit);
}
```

> **Prints:**  
> 0  
> 1  
> 2  
> 3  
> 4  
> 5  
> 6  
> 7  
> 8  
> 9

This makes the for...of loop the most concise version of all the for loops.

> **TIP:** It’s good practice to use plural names for objects that are collections of values. That way, when you loop over the collection, you can use the singular version of the name when referencing individual values in the collection. For example, `for (const button of buttons) {...}`.

But wait, there’s more! The for...of loop also has some additional benefits that fix the weaknesses of the for and for...in loops.

You can stop or break a **for...of loop** at anytime.

```
const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (const digit of digits) {
  if (digit % 2 === 0) {
    continue;
  }
  console.log(digit);
}

```

> **Prints:**  
> 1  
> 3  
> 5  
> 7  
> 9

And you don’t have to worry about adding new properties to objects. The **for...of loop** will only loop over the values in the object.

```
Array.prototype.decimalfy = function() {
  for (i = 0; i < this.length; i++) {
    this[i] = this[i].toFixed(2);
  }
};

const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (const digit of digits) {
  console.log(digit);
}
```

> **Prints:**  
> 0  
> 1  
> 2  
> 3  
> 4  
> 5  
> 6  
> 7  
> 8  
> 9

This time, the properties were not printed out to the console, like we saw on the prior page.

## Topic 3: Spread Operator `...`

The **spread operator**, written with three consecutive dots ( `...` ), is new in ES6 and gives you the ability to expand, or _spread_, [iterable objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#Iterators) into multiple elements.

Let’s take a look at a few examples to see how it works.

```
const books = ["Don Quixote", "The Hobbit", "Alice in Wonderland", "Tale of Two Cities"];
console.log(...books);
```

> **Prints:** Don Quixote The Hobbit Alice in Wonderland Tale of Two Cities

```
const primes = new Set([2, 3, 5, 7, 11, 13, 17, 19, 23, 29]);
console.log(...primes);
```

> **Prints:** 2 3 5 7 11 13 17 19 23 29

If you look at the output from the examples, notice that both the array and set have been expanded into their individual elements. So how is this useful?

> **NOTE:** Sets are a new built-in object in ES6 that we’ll cover in more detail in a future lesson.

### Combining arrays with `concat`

One example of when the spread operator can be useful is when combining arrays.

If you’ve ever needed to combine multiple arrays, prior to the spread operator, you were forced to use the Array’s `concat()` method.

```
const fruits = ["apples", "bananas", "pears"];
const vegetables = ["corn", "potatoes", "carrots"];
const produce = fruits.concat(vegetables);
console.log(produce);
```

> **Prints:** ["apples", "bananas", "pears", "corn", "potatoes", "carrots"]

This isn’t terrible, but wouldn’t it be nice if there was a shorthand way to write this code?

For example, something like…

> #### Upcoming `const` Warning ⚠️
> 
> If you're following along by copy/pasting the code, then you've already declared the `produce` variable with the `const` keyword. The following code will try to redeclare _and_ reassign the variable, so depending on how you're running the code, it might throw an error.
> 
> Remember that variables declared with `const` cannot be redeclared or reassigned in the same scope.

```
const produce = [fruits, vegetables];
console.log(produce);
```

> **Prints:** [Array[3], Array[3]]

Unfortunately, that doesn’t work.

Instead of combining both arrays, this code actually adds the `fruits` array at the first index and the `vegetables` array at the second index of the `produce` array.

### Combining arrays with spread operator

```
/*
 * Instructions: Use the spread operator to combine the `fruits` and `vegetables` arrays into the `produce` array.
 */

const fruits = ["apples", "bananas", "pears"];
const vegetables = ["corn", "potatoes", "carrots"];

const produce = [...fruits,...vegetables];

console.log(produce);
```

> **Prints:** [ 'apples', 'bananas', 'pears', 'corn', 'potatoes', 'carrots' ]

## Topic 3: Rest Parameter `...`

The **rest parameter**, also written with three consecutive dots ( `...` ), allows you to represent an indefinite number of elements as an array. This can be helpful in a couple of different situations.

### Situation 1

One situation is when assigning the values of an array to variables. For example,

```
const order = [20.17, 18.67, 1.50, "cheese", "eggs", "milk", "bread"];
const [total, subtotal, tax, ...items] = order;
console.log(total, subtotal, tax, items)
```

> **Prints:** 20.17 18.67 1.5 ["cheese", "eggs", "milk", "bread"]

This code takes the values of the `order` array and assigns them to individual variables using destructuring (as you saw in the **Destructuring** section earlier in this lesson). `total`, `subtotal`, and `tax` are assigned the first three values in the array, however, `items` is where you want to pay the most attention.

By using the rest parameter, `items` is assigned the rest of the values in the array (as an array).

_You can think of the **rest parameter** like the opposite of the **spread operator**; if the spread operator is like unboxing all of the contents of a package, then the rest parameter is like taking all the contents and putting them back into the package._

### Situation 2: Variadic Functions

Another use case for the rest parameter is when you’re working with variadic functions. **Variadic functions** are functions that take an indefinite number of arguments.

For example, let’s say we have a function called sum() which calculates the sum of an indefinite amount of numbers. How might the sum() function be called during execution?

```
sum(1, 2);
sum(10, 36, 7, 84, 90, 110);
sum(-23, 3000, 575000);
```

There’s literally an endless number of ways the `sum()` function could be called. Regardless of the amount of numbers passed to the function, it should always return the total sum of the numbers.

#### Using the arguments object

In previous versions of JavaScript, this type of function would be handled using the [arguments object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments). The **arguments object** is an array-like object that is available as a local variable inside all functions. It contains a value for each argument being passed to the function starting at 0 for the first argument, 1 for the second argument, and so on.

If we look at the implementation of our `sum()` function, then you’ll see how the arguments object could be used to handle the variable amount of numbers being passed to it.

```
function sum() {
  let total = 0;  
  for(const argument of arguments) {
    total += argument;
  }
  return total;
}
```

Now this works fine, but it does have its issues:

1.  If you look at the definition for the `sum()` function, it doesn’t have any parameters.
    -   This is misleading because we know the `sum()` function can handle an indefinite amount of arguments.
2.  It can be hard to understand.
    -   If you’ve never used the arguments object before, then you would most likely look at this code and wonder where the arguments object is even coming from. Did it appear out of thin air? It certainly looks that way.

#### Using the rest parameter

Fortunately, with the addition of the rest parameter, you can rewrite the `sum()` function to read more clearly.

```
function sum(...nums) {
  let total = 0;  
  for(const num of nums) {
    total += num;
  }
  return total;
}
```

This version of the `sum()` function is both **more concise** and is **easier to read**. Also, notice the `for...in` loop has been replaced with the new [for...of loop](https://classroom.udacity.com/nanodegrees/nd016/parts/11a45d59-bb81-44a9-be76-042c99e5f051/modules/cbf6deb8-d2cc-4757-b3a9-a1c58a4acd82/lessons/42383e89-ac6a-491a-b7d0-198851287bbe/concepts/f1955923-744a-4906-8f64-1ddcb34c6da2#).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTcxMjQ2MDg2OV19
-->
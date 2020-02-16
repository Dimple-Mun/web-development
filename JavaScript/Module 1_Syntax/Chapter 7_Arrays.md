# Chapter 8: Arrays

[intro-to-javascript](https://cn.udacity.com/course/intro-to-javascript--ud803) ([backup](https://classroom.udacity.com/courses/ud803))

## Declaring an Array

An  **array**  is useful because it stores multiple values into a single, organized data structure. You can define a new array by listing values separated with commas `,` between square brackets  `[]`.
```
var arrayName = [element1, element2, ..., elementN];
```

```
// creates a `donuts` array with three strings
var donuts = ["glazed", "powdered", "jelly"];
```

But strings aren’t the only type of data you can store in an array. You can also store numbers, booleans… and really anything!

```
// creates a `mixedData` array with mixed data types
var mixedData = ["abcd", 1, true, undefined, null, "all the things"];
```

You can even store an array in an array to create a  **nested array**!

```
// creates a `arraysInArrays` array with three arrays
var arraysInArrays = [[1, 2, 3], ["Julia", "James"], [true, false, true, false]];
```

Nested arrays can be particularly hard to read, so it's common to write them on one line, using a newline after each comma:

```
var arraysInArrays = [
  [1, 2, 3], 
  ["Julia", "James"], 
  [true, false, true, false]
];
```

## Accessing Array Elements

### Indexing: Array Index

Remember that elements in an array are indexed starting at the position  `0`. To access an element in an array, use the name of the array immediately followed by square brackets containing the index of the value you want to access.
```
arrayName[index]
```
### Reading an Element's Value
```
var donuts = ["glazed", "powdered", "sprinkled"];
console.log(donuts[0]); // "glazed" is the first element in the `donuts` array
```

> **Prints:**  "glazed"

One thing to be aware of is if you try to access an element at an index that does not exist, a value of undefined will be returned back.

```
var donuts = ["glazed", "powdered", "sprinkled"];;
console.log(donuts[3]); // the fourth element in `donuts` array does not exist!
```

> **Prints:**  undefined

[](https://classroom.udacity.com/courses/ud803/lessons/378e7ff7-f7e5-4487-b5c4-fdf9b5c351d9/concepts/5e34b2b4-b6da-4c90-8263-17be965b3cfa#)

![Image showing 3 donuts in spaces 0, 1, and 2, and showing a red X through the space 3](https://video.udacity-data.com/topher/2016/December/583fa854_donut-out-of-bounds/donut-out-of-bounds.jpeg)

Avoid accessing elements outside the bounds of an array. If you try to, the missing element will be returned back as  `undefined`  !

### Changing an Element's Value
Finally, if you want to change the value of an element in array, you can do so by setting it equal to a new value.

```
donuts[1] = "glazed cruller"; // changes the second element in the `donuts` array to "glazed cruller"
console.log(donuts[1]); 
```

> **Prints:**  "glazed cruller"

## Array Properties and Methods

### Properties

**Some common array methods**
- length

#### Array.length

You can find the  **length**  of an array by using its  `length`  property.

```
var donuts = ["glazed", "powdered", "sprinkled"];
console.log(donuts.length);
```

> **Prints:**  3

To access the  `length`  property, type the name of the array, followed by a period  `.`  (you’ll also use the period to access other properties and methods), and the word  `length`. The  `length`  property will then return the  **number of elements**  in the array.

> **TIP:**  Strings have a  `length`  property too! You can use it to get the length of any string. For example,  `"supercalifragilisticexpialidocious".length`  returns  `34`.
### Methods
You can think of methods like special predefined functions that a data structure can call.

> **TIP:** JavaScript provides a large number of built-in methods for modifying arrays and accessing values in an array, check out the [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array), or type `[]`. into the JavaScript console for a list of all the available Array methods.

**Some common array methods**
- reverse
- sort
- push & pop

#### Array.push()

> [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push): The `push()` method adds one or more elements to the end of an array and returns the new length of the array.

```
arr.push(element1[, ...[, elementN]])
```
You can use the  `push()`  method to add elements to the  _end of an array_.

For example, imagine the following spread of donuts.

[](https://classroom.udacity.com/courses/ud803/lessons/378e7ff7-f7e5-4487-b5c4-fdf9b5c351d9/concepts/efeb60e4-d525-401b-b4c3-1bf02d3bfb3f#)

![An image showing 6 varieties of donuts](https://video.udacity-data.com/topher/2016/December/58405293_donut-spread/donut-spread.jpeg)

A spread of donuts. Yummy!

You can represent the spread of donuts using an array.

```
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled"];
```

Then, you can  _push_  donuts onto the end of the array using the  `push()`  method.

```
donuts.push("powdered"); 
// pushes "powdered" onto the end of the `donuts` array
// the `push()` method returns 7 because the `donuts` array now has 7 elements
```

> **Returns:** 7  
> **donuts array:**  ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled", "powdered"]

Notice, with the  `push()`  method you need to pass the value of the element you want to add to the end of the array. Also, the  `push()`  method returns the length of the array after an element has been added.

#### Array.pop()

Alternatively, you can use the  `pop()`  method to remove elements from the  _end of an array_.

```
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled", "powdered"];

donuts.pop(); // pops "powdered" off the end of the `donuts` array
donuts.pop(); // pops "sprinkled" off the end of the `donuts` array
donuts.pop(); // pops "cinnamon sugar" off the end of the `donuts` array
/* the `pop()` method returns "powdered" because "powdered" was the last element on the end of `donuts` array */
```

> **Returns:** "cinnamon sugar"  
> **donuts array:**  ["glazed", "chocolate frosted", "Boston creme", "glazed cruller"]

With the `pop()` method you don’t need to pass a value; instead, `pop()` will always remove the last element from the end of the array. Also, `pop()` returns the element that has been removed in case you need to use it.

#### Array.splice()

`splice()`  is another handy method that allows you to add and remove elements from anywhere within an array.

While  `push()`  and  `pop()`  limit you to adding and removing elements from  _the end of an array_,  `splice()`  lets you specify the index location to add new elements, as well as the number of elements you'd like to delete (if any).

```
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller"];
donuts.splice(1, 1, "chocolate cruller", "creme de leche"); // removes "chocolate frosted" at index 1 and adds "chocolate cruller" and "creme de leche" starting at index 1
```

> **Returns:**  ["chocolate frosted"]  
> **donuts array:**  ["glazed", "chocolate cruller", "creme de leche", "Boston creme", "glazed cruller"]

The first argument represents the starting index from where you want to change the array, the second argument represents the numbers of elements you want to remove, and the remaining arguments represent the elements you want to add.

`splice()`  is an incredibly powerful method that allows you to manipulate your arrays in a variety of ways. Any combination of adding or removing elements from an array can all be done in one simple line of code.

Take a look at the  [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)  to see a long list of example code snippets demonstrating the power of  `splice()`  and then try the next set of programming quizzes.

#### Array.reverse()
> [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse): The `reverse()` method reverses an array _[in place](https://en.wikipedia.org/wiki/In-place_algorithm)_. The first array element becomes the last, and the last array element becomes the first.

```
arr.reverse()
```

#### Array.shift()
> [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift): The `shift()` method removes the **first** element from an array and returns that removed element. This method changes the length of the array.

```
arr.shift()
```

```
const elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());
// expected output: "Fire,Air,Water"

console.log(elements.join(''));
// expected output: "FireAirWater"

console.log(elements.join('-'));
// expected output: "Fire-Air-Water"
```

#### Array.join()

> [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join): The  `join()`  method creates and returns a new string by concatenating all of the elements in an array (or an  [array-like object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#Working_with_array-like_objects)), separated by commas or a specified separator string. If the array has only one item, then that item will be returned without using the separator.
```
arr.join([separator])
```

## Array Loops

Once the data is in the array, you want to be able to efficiently access and manipulate each element in the array without writing repetitive code for each element.

For instance, if this was our original donuts array:

```
var donuts = ["jelly donut", "chocolate donut", "glazed donut"];
```

and we decided to make all the same donut types, but only sell them as  _donut holes_  instead, we could write the following code:

```
donuts[0] += " hole";
donuts[1] += " hole";
donuts[2] += " hole";
```

> **donuts array:**  ["jelly donut hole", "chocolate donut hole", "glazed donut hole"]

But remember, you have another powerful tool at your disposal,  **loops**!

### For Loops
To loop through an array, you can use a variable to represent the index in the array, and then loop over that index to perform whatever manipulations your heart desires.

```
var donuts = ["jelly donut", "chocolate donut", "glazed donut"];

// the variable `i` is used to step through each element in the array
for (var i = 0; i < donuts.length; i++) {
    donuts[i] += " hole";
    donuts[i] = donuts[i].toUpperCase();
}

```

> **donuts array:**  ["JELLY DONUT HOLE", "CHOCOLATE DONUT HOLE", "GLAZED DONUT HOLE"]

In this example, the variable  `i`  is being used to represent the index of the array. As  `i`  is incremented, you are stepping over each element in the array starting from  `0`  until  `donuts.length - 1`  (`donuts.length`  is out of bounds).

### The forEach() Loop
Arrays have a set of special methods to help you iterate over and perform operations on collections of data. You can view the MDN Documentation list of Array methods  [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array), but a couple big ones to know are the  `forEach()`  and  `map()`  methods.

The  `forEach()`  method gives you an alternative way to iterate over an array, and manipulate each element in the array with an inline function expression.

```
var donuts = ["jelly donut", "chocolate donut", "glazed donut"];

donuts.forEach(function(donut) {
  donut += " hole";
  donut = donut.toUpperCase();
  console.log(donut);
  return donut;
});

console.log(donuts);
```
> **Prints:**  
> JELLY DONUT HOLE  
> CHOCOLATE DONUT HOLE  
> GLAZED DONUT HOLE
> ["jelly donut", "chocolate donut", "glazed donut"]

```
var donuts = ["jelly donut", "chocolate donut", "glazed donut"];

donuts.forEach(function(donut,donutIndex,arr) {
  donut += " hole";
  donut = donut.toUpperCase();
  console.log(donut);
  arr[donutIndex] = donut;
  return arr;
});

console.log(donuts);
```

> **Prints:**
JELLY DONUT HOLE
CHOCOLATE DONUT HOLE
GLAZED DONUT HOLE
["JELLY DONUT HOLE", "CHOCOLATE DONUT HOLE", "GLAZED DONUT HOLE"]

Notice that the  `forEach()`  method iterates over the array without the need of an explicitly defined index. In the example above,  `donut`  corresponds to the element in the array itself. This is different from a  `for`  or  `while`  loop where an index is used to access each element in the array:

```
for (var i = 0; i < donuts.length; i++) {
  donuts[i] += " hole";
  donuts[i] = donuts[i].toUpperCase();
  console.log(donuts[i]);
}
```

#### Parameters

> The `forEach()` method executes a provided function once for each array element.

```
arr.forEach(callBack(currentValue, index, array){},thisArg)
```
- `callback`
Function to execute on each element. It accepts between one and three arguments:

	- `currentValue`
	The current element being processed in the array.

	- `index`  *Optional*
	The index  `currentValue` in the array.

	- `array`  *Optional*
	The array  `forEach()`  was called upon.

- `thisArg`  *Optional*
Value to use as  `this`  when executing  `callback`.

The function that you pass to the  `forEach()`  method can take up to three parameters. In the video, these are called  `element`,  `index`, and  `array`, but you can call them whatever you like.

The  `forEach()`  method will call this function once  _for each_  element in the array (hence the name  `forEach`.) Each time, it will call the function with different arguments. The  `element`  parameter will get the  _value_  of the array element. The  `index`  parameter will get the  _index_  of the element (starting with zero). The  `array`  parameter will get a reference to the whole array, which is handy if you want to modify the elements.

Here's another example:

```
words = ["cat", "in", "hat"];
words.forEach(function(word, num, all) {
  console.log("Word " + num + " in " + all.toString() + " is " + word);
});
```

> **Prints:**  
> Word 0 in cat,in,hat is cat  
> Word 1 in cat,in,hat is in  
> Word 2 in cat,in,hat is hat

On the next page, you'll do a quiz that uses the  `forEach()`  method to modify an array.

#### Exercise
- **Directions:**

	Use the array's  `forEach()`  [method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)  to loop over the following array and add  `100`  to each of the values if the value is divisible by  `3`.

	```
	var test = [12, 929, 11, 3, 199, 1000, 7, 1, 24, 37, 4, 19, 300, 3775, 299, 36, 209, 148, 169, 299, 6, 109, 20, 58, 139, 59, 3, 1, 139];
	```

	Remember that the "Test Run" button will display any logged content, so feel free to use  `console.log()`  to test your code.

- **Your Code:**
	```
	/*
	 * Programming Quiz: Another Type of Loop (6-8)
	 *
	 * Use the existing `test` variable and write a `forEach` loop
	 * that adds 100 to each number that is divisible by 3.
	 *
	 * Things to note:
	 *  - you must use an `if` statement to verify code is divisible by 3
	 *  - you can use `console.log` to verify the `test` variable when you're finished looping
	 */

	var test = [12, 929, 11, 3, 199, 1000, 7, 1, 24, 37, 4,
	    19, 300, 3775, 299, 36, 209, 148, 169, 299,
	    6, 109, 20, 58, 139, 59, 3, 1, 139
	];

	// Write your code here
	test.forEach(function(element, index){
	    if(element % 3 === 0) {
	        test[index] = element + 100;
	    }
	})

	console.log(test);
	```

### Array.map()
Using  `forEach()`  will not be useful if you want to permanently modify the original array.  `forEach()`  always returns  `undefined`. However, creating a new array from an existing array is simple with the powerful  `map()`  method.

With the  `map()`  [method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map), you can take an array, perform some operation on each element of the array, and return a new array.

```
var donuts = ["jelly donut", "chocolate donut", "glazed donut"];

var improvedDonuts = donuts.map(function(donut) {
  donut += " hole";
  donut = donut.toUpperCase();
  return donut;
});
```

> **donuts array:**  ["jelly donut", "chocolate donut", "glazed donut"]  
> **improvedDonuts array:**  ["JELLY DONUT HOLE", "CHOCOLATE DONUT HOLE", "GLAZED DONUT HOLE"]

Oh man, did you just see that? The  `map()`  method accepts one argument, a function that will be used to manipulate each element in the array. In the above example, we used a function expression to pass that function into  `map()`. This function is taking in one argument,  `donut`  which corresponds to each element in the  `donuts`  array. You no longer need to iterate over the indices anymore.  `map()`  does all that work for you.

#### Exercise
- **Directions:**

	Use the  `map()`  [method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)  to take the array of bill amounts shown below, and create a second array of numbers called  `totals`  that shows the bill amounts with a 15% tip added.

	```
	var bills = [50.23, 19.12, 34.01, 100.11, 12.15, 9.90, 29.11, 12.99, 10.00, 99.22, 102.20, 100.10, 6.77, 2.22];
	```

	Print out the new  `totals`  array using  `console.log`.

	> **TIP:**  Check out the  `toFixed()`  method for numbers to help with  [rounding](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed)  the values to a maximum of 2 decimal places. Note, that the method returns a string to maintain the "fixed" format of the number. So, if you want to convert the string back to a number, you can  **cast**  it or convert it back to a number:

	```
	Number("1");
	```

	> **Returns:**  1

- **Your Code:**
	```
	/*
	 * Programming Quiz: I Got Bills (6-9)
	 *
	 * Use the .map() method to take the bills array below and create a second array
	 * of numbers called totals. The totals array should contains each amount from the
	 * bills array but with a 15% tip added. Log the totals array to the console.
	 *
	 * For example, the first two entries in the totals array would be:
	 *
	 * [57.76, 21.99, ... ]
	 *
	 * Things to note:
	 *  - each entry in the totals array must be a number
	 *  - each number must have an accuracy of two decimal points
	 */

	var bills = [50.23, 19.12, 34.01,
	    100.11, 12.15, 9.90, 29.11, 12.99,
	    10.00, 99.22, 102.20, 100.10, 6.77, 2.22
	];

	var totals = bills.map(function(bill) {
	    bill = bill*1.15;
	    bill = Number(bill.toFixed(2));
	    return bill;
	})

	console.log(totals);
	```

### 问题？？？
```
/*
 * Programming Quiz: I Got Bills (6-9)
 *
 * Use the .map() method to take the bills array below and create a second array
 * of numbers called totals. The totals array should contains each amount from the
 * bills array but with a 15% tip added. Log the totals array to the console.
 *
 * For example, the first two entries in the totals array would be:
 *
 * [57.76, 21.99, ... ]
 *
 * Things to note:
 *  - each entry in the totals array must be a number
 *  - each number must have an accuracy of two decimal points
 */

var bills = [50.23, 19.12, 34.01,
    100.11, 12.15, 9.90, 29.11, 12.99,
    10.00, 99.22, 102.20, 100.10, 6.77, 2.22
];

var totals = bills.map(function(bill) {
    total = bill*1.15; //为什么 total 没有被声明却可以被调用
    total = Number(total.toFixed(2));
    return total;
})

console.log(totals);
```

## 2D Arrays (Arrays in Arrays)

Oftentimes, donuts are arranged in a grid.
You could use an array of arrays that has the name of each donut associated with its position in the box.

Here's an example:

```
var donutBox = [
  ["glazed", "chocolate glazed", "cinnamon"],
  ["powdered", "sprinkled", "glazed cruller"],
  ["chocolate cruller", "Boston creme", "creme de leche"]
];

```

If you wanted to loop over the donut box and display each donut (along with its position in the box!) you would start with writing a  `for`  loop to loop over each row of the box of donuts:

```
var donutBox = [
  ["glazed", "chocolate glazed", "cinnamon"],
  ["powdered", "sprinkled", "glazed cruller"],
  ["chocolate cruller", "Boston creme", "creme de leche"]
];

// here, donutBox.length refers to the number of rows of donuts
for (var row = 0; row < donutBox.length; row++) {
  console.log(donutBox[row]);
}

```

> **Prints:**  
> ["glazed", "chocolate glazed", "cinnamon"]  
> ["powdered", "sprinkled", "glazed cruller"]  
> ["chocolate cruller", "Boston creme", "creme de leche"]

Since each row is an array of donuts, you next need to set up an inner-loop to loop over each cell in the arrays.

```
for (var row = 0; row < donutBox.length; row++) {
  // here, donutBox[row].length refers to the length of the donut array currently being looped over
  for (var column = 0; column < donutBox[row].length; column++) {
    console.log(donutBox[row][column]);
  }
}
```

> **Prints:**  
> "glazed"  
> "chocolate glazed"  
> "cinnamon"  
> "powdered"  
> "sprinkled"  
> "glazed cruller"  
> "chocolate cruller"  
> "Boston creme"  
> "creme de leche"


### Exercise
- **Directions:**

	Use a nested  `for`  loop to take the  `numbers`  array below and replace all of the values that are divisible by  `2`  (even numbers) with the string "even" and all other numbers with the string "odd".

	```
	var numbers = [
	    [243, 12, 23, 12, 45, 45, 78, 66, 223, 3],
	    [34, 2, 1, 553, 23, 4, 66, 23, 4, 55],
	    [67, 56, 45, 553, 44, 55, 5, 428, 452, 3],
	    [12, 31, 55, 445, 79, 44, 674, 224, 4, 21],
	    [4, 2, 3, 52, 13, 51, 44, 1, 67, 5],
	    [5, 65, 4, 5, 5, 6, 5, 43, 23, 4424],
	    [74, 532, 6, 7, 35, 17, 89, 43, 43, 66],
	    [53, 6, 89, 10, 23, 52, 111, 44, 109, 80],
	    [67, 6, 53, 537, 2, 168, 16, 2, 1, 8],
	    [76, 7, 9, 6, 3, 73, 77, 100, 56, 100]
	];

	```

- **Your Code:**
	- Solution 1
	```
	/*
	 * Programming Quiz: Nested Numbers (6-10)
	 *
	 *   - The `numbers` variable is an array of arrays.
	 *   - Use a nested `for` loop to cycle through `numbers`.
	 *   - Convert each even number to the string "even"
	 *   - Convert each odd number to the string "odd"
	 */

	var numbers = [
	    [243, 12, 23, 12, 45, 45, 78, 66, 223, 3],
	    [34, 2, 1, 553, 23, 4, 66, 23, 4, 55],
	    [67, 56, 45, 553, 44, 55, 5, 428, 452, 3],
	    [12, 31, 55, 445, 79, 44, 674, 224, 4, 21],
	    [4, 2, 3, 52, 13, 51, 44, 1, 67, 5],
	    [5, 65, 4, 5, 5, 6, 5, 43, 23, 4424],
	    [74, 532, 6, 7, 35, 17, 89, 43, 43, 66],
	    [53, 6, 89, 10, 23, 52, 111, 44, 109, 80],
	    [67, 6, 53, 537, 2, 168, 16, 2, 1, 8],
	    [76, 7, 9, 6, 3, 73, 77, 100, 56, 100]
	];

	// your code goes here
	var eachRow;
	for(var row = 0; row < numbers.length; row++) {
	    eachRow = numbers[row];
	    for(var col = 0; col < eachRow.length; col++) {
	        if(eachRow[col] % 2 === 0) {
	            numbers[row][col] = "even";
	        } else {
	            numbers[row][col] = "odd";
	        }
	    }
	}

	console.log(numbers);
	```
	- Solution 2
	```
	var numbers = [
	    [243, 12, 23, 12, 45, 45, 78, 66, 223, 3],
	    [34, 2, 1, 553, 23, 4, 66, 23, 4, 55],
	    [67, 56, 45, 553, 44, 55, 5, 428, 452, 3],
	    [12, 31, 55, 445, 79, 44, 674, 224, 4, 21],
	    [4, 2, 3, 52, 13, 51, 44, 1, 67, 5],
	    [5, 65, 4, 5, 5, 6, 5, 43, 23, 4424],
	    [74, 532, 6, 7, 35, 17, 89, 43, 43, 66],
	    [53, 6, 89, 10, 23, 52, 111, 44, 109, 80],
	    [67, 6, 53, 537, 2, 168, 16, 2, 1, 8],
	    [76, 7, 9, 6, 3, 73, 77, 100, 56, 100]
	];

	// your code goes here
	numbers.map(function(eachRow) {
	    for(var col = 0; col < eachRow.length; col++) {
	        if(eachRow[col] % 2 === 0) {
	            eachRow[col] = "even";
	        }else {
	            eachRow[col] = "odd";
	        }
	    }
	    return eachRow;
	})

	console.log(numbers);
	```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjU2OTc2OTM1XX0=
-->
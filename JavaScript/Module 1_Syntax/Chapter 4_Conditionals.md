# Chapter 4: Conditionals

[intro-to-javascript](https://cn.udacity.com/course/intro-to-javascript--ud803) ([backup](https://classroom.udacity.com/courses/ud803))

```
if (/* this expression is true */) {
  // run this code;
  // 必须保留至少一个条件语句，即`if`语句是必要的，其他`else if`或`else`语句是可选的;
} else if (/* this expression is true */) {
  // run this code;
} else if (/* this expression is true */) {
  // run this code;
} else {
  // run this code;
}
```

## Intro to Conditionals

### 1. Flowchart 
> **DEFINITION:** A **flowchart** is a visual diagram that outlines the solution to a problem through a series of logical statements. The order in which statements are evaluated and executed is called the **control flow**.

**Supporting Materials**

[Purchase-The-Item-Flowchart](http://video.udacity-data.com.s3.amazonaws.com/topher/2017/January/586e9791_purchase-the-item-flowchart/purchase-the-item-flowchart.jpg)

[Approaching-The-Castle-Flowchart](http://video.udacity-data.com.s3.amazonaws.com/topher/2017/January/586e979e_approaching-the-castle-flowchart/approaching-the-castle-flowchart.jpg)

### 2. Flowchart  to Code
- **Break Down Problems** into small steps
- Using **Conditional Statements & Logical Operators** to create algorithms to solve problems
	- Conditional Statements
		- If ...else statement & Else if statement
	- Logical Operators
		- `&&`, `||`, `!`
- **Advanced Techniques**
	- Truthy Falsy
	- Ternary Operators
	- Switch Statements

## Conditional Statements

### If...else statements

**If...else statements**  allow you to execute certain pieces of code based on a condition, or set of conditions, being met.

```
if (/* this expression is true */) {
  // run this code
} else {
  // run this code
}

```

This is extremely helpful because it allows you to choose which piece of code you want to run based on the result of an expression. For example,

```
var a = 1;
var b = 2;

if (a > b) {
  console.log("a is greater than b");
} else {
  console.log("a is less than or equal to b");
}

```

> **Prints:**  "a is less than or equal to b"

A couple of important things to notice about  `if...else`  statements.

The value inside the  `if`  statement is always  _converted_  to true or false. Depending on the value, the code inside the  `if`  statement is run or the code inside the  `else`  statement is run, but not both. The code inside the  `if`  and  `else`  statements are surrounded by  **curly braces**  `{...}`  to separate the conditions and indicate which code should be run.

> **TIP:**  When coding, sometimes you may  _only_  want to use an  `if`  statement. However, if you try to use only an  `else`  statement, then you will receive the error  `SyntaxError: Unexpected token else`. You’ll see this error because  `else`  statements need an  `if`  statement in order to work. You can’t have an  `else`  statement without first having an  `if`  statement.

### Else if statements

In JavaScript, you can represent this secondary check by using an extra if statement called an  **else if statement**.

```
var weather = "sunny";

if (weather === "snow") {
  console.log("Bring a coat.");
} else if (weather === "rain") {
  console.log("Bring a rain jacket.");
} else {
  console.log("Wear what you have on.");
}

```

> **Prints:**  Wear what you have on.

## Conditional Statements with Logical Operators

## Advanced Techniques
### Ternary operator
Sometimes, you might find yourself with the following type of conditional.

```
var isGoing = true;
var color;

if (isGoing) {
  color = "green";
} else {
  color = "red";
}

console.log(color);
```

> **Prints:**  "green"

In this example, the variable  `color`  is being assigned to either  `"green"`  or  `"red"`  based on the value of  `isGoing`. This code works, but it’s a rather lengthy way for assigning a value to a variable. Thankfully, in JavaScript there’s another way--**ternary operator**.

> **TIP:**  Using  `if(isGoing)`  is the same as using  `if(isGoing === true)`. Alternatively, using  `if(!isGoing)`  is the same as using  `if(isGoing === false)`.

**Ternary Operator**

The  **ternary operator**  provides you with a shortcut alternative for writing lengthy if...else statements.

```
conditional ? (if condition is true) : (if condition is false)

```

To use the ternary operator, first provide a conditional statement on the left-side of the  `?`. Then, between the  `?`  and  `:`  write the code that would run if the condition is  `true`  and on the right-hand side of the  `:`  write the code that would run if the condition is  `false`. For example, you can rewrite the example code above as:

```
var isGoing = true;
var color = isGoing ? "green" : "red";
console.log(color);

```

> **Prints:**  "green"

This code not only replaces the conditional, but it also handles the variable assignment for  `color`.

If you breakdown the code, the condition  `isGoing`  is placed on the left side of the  `?`. Then, the first expression, after the  `?`, is what will be run if the condition is  _true_  and the second expression after the,  `:`, is what will be run if the condition is  _false_.

### Switch statement

A  **switch statement**  is an another way to chain multiple  `else if`  statements that are based on the same value  **without using conditional statements**. Instead, you just  _switch_  which piece of code is executed based on a value.

```
switch (option) {
  case 1:
    console.log("You selected option 1.");
  case 2:
    console.log("You selected option 2.");
  case 3:
    console.log("You selected option 3.");
  case 4:
    console.log("You selected option 4.");
  case 5:
    console.log("You selected option 5.");
  case 6:
    console.log("You selected option 6.");
}

```

Here, each  `else if`  statement (`option === [value]`) has been replaced with a  `case`  clause (`case: [value]`) and those clauses have been wrapped inside the switch statement.

When the switch statement first evaluates, it looks for the first  `case`  clause whose expression evaluates to the same value as the result of the expression passed to the switch statement. Then, it transfers control to that  `case`  clause, executing the associated statements.

So, if you set  `option`  equal to  `3`...

```
var option = 3;

switch (option) {
  ...
}

```

> **Prints:**  
> You selected option 3.  
> You selected option 4.  
> You selected option 5.  
> You selected option 6.

...then the switch statement prints out options 3, 4, 5, and 6.

But that’s not exactly like the original  `if...else`  code at the top? So what’s missing?

#### Break statement

The  **break statement**  can be used to terminate a switch statement and transfer control to the code following the terminated statement. By adding a  `break`  to each  `case`  clause, you fix the issue of the switch statement  _falling-through_  to other case clauses.

```
var option = 3;

switch (option) {
  case 1:
    console.log("You selected option 1.");
    break;
  case 2:
    console.log("You selected option 2.");
    break;
  case 3:
    console.log("You selected option 3.");
    break;
  case 4:
    console.log("You selected option 4.");
    break;
  case 5:
    console.log("You selected option 5.");
    break;
  case 6:
    console.log("You selected option 6.");
    break; // technically, not needed
}

```

> **Prints:**  You selected option 3.

```
var month = 2;

switch(month) {
  case 1:
  case 3:
  case 5:
  case 7:
  case 8:
  case 10:
  case 12:
    days = 31;
    break;
  case 4:
  case 6:
  case 9:
  case 11:
    days = 30;
    break;
  case 2:
    days = 28;
}

console.log("There are " + days + " days in this month.");
```

> **Prints:**  There are 28 days in this month.

#### Falling-through

In some situations, you might want to leverage the "falling-through" behavior of switch statements to your advantage.

For example, when your code follows a hierarchical-type structure.

```
var tier = "nsfw deck";
var output = "You’ll receive "

switch (tier) {
  case "deck of legends":
    output += "a custom card, ";
  case "collector's deck":
    output += "a signed version of the Exploding Kittens deck, ";
  case "nsfw deck":
    output += "one copy of the NSFW (Not Safe for Work) Exploding Kittens card game and ";
  default:
    output += "one copy of the Exploding Kittens card game.";
}

console.log(output);

```

> **Prints:**  You’ll receive one copy of the NSFW (Not Safe for Work) Exploding Kittens card game and one copy of the Exploding Kittens card game.

In this example, based on the  [successful Exploding Kittens Kickstarter campaign](https://www.kickstarter.com/projects/elanlee/exploding-kittens/description)  (a hilarious card game created by Elan Lee), each successive tier builds on the next by adding more to the output. Without any break statements in the code, after the switch statement jumps to the  `"nsfw deck"`, it continues to fall-through until reaching the end of the switch statement.

Also, notice the  `default`  case.

```
var tier = "none";
var output = "You’ll receive ";

switch (tier) {
  ... 
  default:
    output += "one copy of the Exploding Kittens card game.";
}

console.log(output);

```

> **Prints:**  You’ll receive one copy of the Exploding Kittens card game.

You can add a  `default`  case to a switch statement and it will be executed when none of the values match the value of the switch expression.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM2ODk3OTc1Ml19
-->
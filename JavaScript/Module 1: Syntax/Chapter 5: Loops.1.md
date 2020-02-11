# Chapter 5: Loops

## While Loops

### Parts of a While Loop

There are many different kinds of loops, but they all essentially do the same thing: they repeat an action some number of times.

Three main pieces of information that any loop should have are:

1.  **When to start:**  The code that sets up the loop — defining the starting value of a variable for instance.
2.  **When to stop:**  The logical condition to test whether the loop should continue.
3.  **How to get to the next item:**  The incrementing or decrementing step — for example,  `x = x * 3`  or  `x = x - 1`

Here's a basic while loop example that includes all three parts.

```
var start = 0; // when to start
while (start < 10) { // when to stop
  console.log(start);
  start = start + 2; // how to get to the next item
}

```

> **Prints:**  
> 0  
> 2  
> 4  
> 6  
> 8

If a loop is missing any of these three things, then you might find yourself in trouble. For instance, a missing stop condition can result in a loop that never ends!

**Don't run this code!**

```
while (true) {
  console.log("true is never false, so I will never stop!");
}

```

If you did try to run that code in the console, you probably crashed your browser tab.

> **WARNING:**  You’re probably reading this because you didn't heed our warnings about running that infinite loop in the console. If your browser tab has crashed or has become frozen/unresponsive, there are a couple ways to fix this. If you are using Firefox, the browser will popup a notification about your script being unresponsive, and will give you the option to kill the script (do that). If you're using Chrome, go to the taskbar and select Window > Task Manager. You can end the process for the particular tab you ran the script in through the task manager. If you’re not using Firefox or Chrome, download Firefox or Chrome ;).

Here's an example where a loop is missing how to get to the next item; the variable  `x`  is never incremented.  `x`  will remain 0 throughout the program, so the loop will never end.

_Don't run this code!_

```
var x = 0;

while (x < 1) {
  console.log('Oops! x is never incremented from 0, so i will ALWAYS be less than 1');
}

```

This code will also crash your browser tab, so we don't recommend running it.

## For Loops
### Parts of a For Loop
The  `for loop`  explicitly forces you to define the **start point**, **stop point**, and **each step of the loop**. In fact, you'll get an  `Uncaught SyntaxError: Unexpected token )`  if you leave out any of the three required pieces.

```
for ( start; stop; step ) {
  // do this thing
}

```

Here's an example of a for loop that prints out the values from 0 to 5. Notice the semicolons separating the different statements of the for loop:  `var i = 0; i < 6; i = i + 1`

```
for (var i = 0; i < 6; i = i + 1) {
  console.log("Printing out i = " + i);
}

```

> **Prints**:  
> Printing out i = 0  
> Printing out i = 1  
> Printing out i = 2  
> Printing out i = 3  
> Printing out i = 4  
> Printing out i = 5
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA4Mjc3MjEwM119
-->
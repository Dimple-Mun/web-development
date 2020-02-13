# Appendix 1: Coding Template
```
var myCustomDiv = document.createElement('div');

function respondToTheClick(evt) {
    if (evt.target.nodeName === 'P'){
        console.log('A paragraph was clicked: ' + evt.target.textContent);
    }
    
}

for (var i = 1; i <= 200; i++) {
    var newElement = document.createElement('p');
    newElement.textContent = 'This is paragraph number ' + i;

    myCustomDiv.appendChild(newElement);
}

document.body.appendChild(myCustomDiv);

myCustomDiv.addEventListener('click', respondToTheClick);
```

# Build a Triangle
## Directions:

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
## Code:
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

# Quiz: Laugh (5-4)
## Directions:

Write an anonymous function expression that stores a function in a variable called "laugh" and outputs the number of "ha"s that you pass in as an argument.

```
laugh(3);

```

> **Returns:**  hahaha!

## Your Code:
```
/*
 * Programming Quiz: Laugh (5-4)
 */

var laugh = function(num) {
    var laughMessage = "";
    for(var i = 0; i < num; i++) {
        laughMessage += "ha";
    }
    laughMessage += "!";
    return laughMessage;
}

console.log(laugh(10));
```

```
/*
 * Programming Quiz: Inline Functions (5-6)
 */

// don't change this code
function emotions(myString, myFunc) {
    console.log("I am " + myString + ", " + myFunc(2));
}

// your code goes here
// call the emotions function here and pass in an
// inline function expression


emotions("happy", function laugh(num) {
    var result = "";
    for (i = 1; i <= num; i++) {
        result += "ha";
    }
    return result += "!";
});
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjAxNjIzMDc1OF19
-->
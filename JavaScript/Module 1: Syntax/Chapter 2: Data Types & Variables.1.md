# Chapter 2: Data Types & Variables

## Comments

You can use  **comments**  to help explain your code and make things clearer. In JavaScript, comments are marked with a double forward-slash  `//`. Anything written on the same line after the  `//`  will not be executed or displayed. To have the comment span multiple lines, mark the start of your comment with a forward-slash and star, and then enclose your comment inside a star and forward-slash  `/* … */`.

```
// this is a single-line comment

/*
this is
a multi-line
comment
*/
```

## Intro to Data Types
### Type 1: Numbers
#### Defining Numbers
Defining a number in JavaScript is actually pretty simple. The  **Number**  data type includes any positive or negative integer, as well as decimals. Entering a number into the console will return it right back to you.

```
3 
```

> **Returns:**  3

There, you did it.

#### Arithmetic Operations

You can also perform calculations with numbers pretty easily. Basically type out an expression the way you would type it in a calculator.

```
3 + 2.1
```

> **Returns:**  5.1

Now you try!

#### Comparing Numbers

What about comparing numbers? Can you do that? Well of course you can!

Just like in mathematics, you can compare two numbers to see if one’s greater than, less than, or equal to the other.

```
5 > 10
```

> **Returns:**  false

```
5 < 10
```

> **Returns:**  true

```
5 == 10
```

> **Returns:**  false

Comparisons between numbers will either evaluate to true or false. Here are some more examples, so you can try it out!

| **Operator** | **Meaning** |
|--|--|
| < | Less than |
| > | Greater than |
| <= | Less than or Equal to |
| >= | Greater than or Equal to |
| == | Equal to |
| != | Not Equal to |

> **TIP:** The values `true` and `false` have significant importance in JavaScript. These values are called **Booleans** and are another data type in JavaScript. Later in this lesson, you’ll learn more about why Booleans are so important in programming.

### Type 2: Strings

**Strings**  are a collection of characters enclosed inside double or single quotes. You can use strings to represent data like sentences, names, addresses, and more.

> **TIP:** It is correct to either use double `"` or single `'` quotes with strings, as long as you're consistent. The [JavaScript Udacity style guide](http://udacity.github.io/frontend-nanodegree-styleguide/javascript.html) for labs and projects suggests using single quotes to define string literals.

#### String Concatenation
Did you know you can even add strings together? In JavaScript, this is called  **concatenating**. Concatenating two strings together is actually pretty simple!

```
'Hello,' + ' New York City'
```

> **Returns:**  "Hello, New York City"

You will see other ways to concatenate and do even more with strings later in this course. But for now, practice using the addition `+` operator.

#### Indexing

Did you know that you can access individual characters in a string? To access an individual character, you can use the character's location in the string, called its  **index**. Just put the index of the character inside square brackets (starting with  `[0]`  as the first character) immediately after the string. For example:

```
"James"[0];

```

> **Returns:**  "J"

or more commonly, you will see it like this, using a variable:

```
var name = "James";
name[0];

```

> **Returns:**  "J"

Characters within a string are indexed starting from 0, where the first character is at position 0, to n-1, where the last character is at position n-1 (n represents the total number of characters within a string).

#### Escaping Strings

There are some cases where you might want to create a string that contains more than just numbers and letters. For example, what if you want to use quotes in a string?

```
"The man whispered, "please speak to me.""

```

> **Uncaught SyntaxError:**  Unexpected identifier

If you try to use quotes within a string, you will receive a  `SyntaxError`  like the one above.

Because you need to use quotes to denote the beginning and end of strings, the JavaScript engine misinterprets the meaning of your string by thinking  `"The man whispered, "`  is the string. Then, it sees the remaining  `please speak to me.""`  and returns a  `SyntaxError`.

If you want to use quotes  _inside a string_, and have JavaScript not misunderstand your intentions, you’ll need a different way to write quotes. Thankfully, JavaScript has a way to do this using the backslash character (  `\`  ).

##### Escaping Characters

In JavaScript, you use the backslash to  **escape**  other characters.

_Escaping a character_  tells JavaScript to ignore the character's special meaning and just use the literal value of the character. This is helpful for characters that have special meanings like in our previous example with quotes  `"…"`.

Because quotes are used to signify the beginning and end of a string, you can use the backslash character to escape the quotes in order to access the literal quote character.

```
"The man whispered, \"please speak to me.\""

```

> **Returns:**  The man whispered, "please speak to me."

This guarantees that the JavaScript engine doesn’t misinterpret the string and result in an error.

##### Special Characters

Quotes aren’t the only  **special characters**  that need to be escaped, there’s actually  [quite a few](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#Using_special_characters_in_strings). However, to keep it simple, here’s a list of some common special characters in JavaScript.

| **Code** | **Character** |
|--|--|
| \\ | \ (backslash) |
| \" | '' (double quote) |
| \' | ' (single quote) |
| \n | newline |
| \t | tab |

The last two characters listed in the table, newline  `\n`  and tab  `\t`, are unique because they add additional  **whitespace**  to your Strings. A newline character will add a line break and a tab character will advance your line to the next  [tab stop](https://en.wikipedia.org/wiki/Tab_stop).

```
"Up up\n\tdown down"

```

> **Returns:**  
> Up up  
>  down down

#### Comparing Strings

Another way to work with strings is by comparing them. You've seen the comparison operators  `==`  and  `!=`  when you compared numbers for equality. You can also use them with strings! For example, let’s compare the string  `"Yes"`  to  `"yes"`.

```
"Yes" == "yes"

```

> **Returns:**  false

When you run this in the console, it returns false. Why is that?  `"Yes"`  and  `"yes"`  are the same string, right? Well not quite.

##### Case-sensitive

When you compare strings, case matters. While both string use the same letters (and those letters appear in the same order), the first letter in the first string is a capital  `Y`  while the first letter in the second string is a lowercase  `y`.

```
'Y' != 'y'
```

> **Returns:**  true

### Type 3: Booleans

### Type 4: Null, Undefined, & NaN
#### Null
`null` refers to the "value of nothing
```
var x = null;
console.log(x);
```
> **Returns:**  null

#### Undefined
`undefined` refers to the "absence of value"
```
var x;
console.log(x);
```
> **Returns:**  undefined

#### NaN
`NaN`  stands for "Not-A-Number" and it's often returned indicating an error with number operations. For instance, if you wrote some code that performed a math calculation, and the calculation failed to produce a valid number,  `NaN`  might be returned.
```
// calculating the square root of a negative number will return NaN
Math.sqrt(-10)

// trying to divide a string by 5 will return NaN
"hello"/5
```

## Storing Data in Variables

With variables, you no longer need to work with one-time-use data.

At the beginning of this course, you declared the value of a string, but you didn't have a way to access or reuse the string later.

```
"Hello"; // Here's a String "Hello"
"Hello" + " World"; // Here's a new String (also with the value "Hello") concatenated with " World"

```

Storing the value of a string in a variable is like packing it away for later use.

```
var greeting = "Hello";
```
Now, if you want to use "Hello" in a variety of sentences, you don't need to duplicate "Hello" strings. You can just reuse the  `greeting`  variable.

```
greeting + " World!";

```

> **Returns:**  Hello World!

```
greeting + " Mike!";

```

> **Returns:**  Hello Mike!

You can also change the start of the greeting by  _reassigning_  a new string value to the variable  `greeting`.

```
greeting = "Hola";
greeting + " World!";

```

> **Returns:**  Hola World!

```
greeting + " Mike!";

```

> **Returns:**  Hola Mike!

### Naming Conventions

When you create a variable, you write the name of the variable using camelCase (the first word is lowercase, and all following words are uppercase). Also try to use a variable name that accurately, but succinctly describes what the data is about.

```
var totalAfterTax = 53.03; // uses camelCase if the variable name is multiple words
var tip = 8; // uses lowercase if the variable name is one word

```

Not using camelCase for your variables names is not going to necessarily  _break_  anything in JavaScript. But there are recommended style guides used in all programming languages that help keep code consistent, clean, and easy-to-read. This is especially important when working on larger projects that will be accessed by multiple developers.

You can read more about Google's JavaScript StyleGuide  [here](https://google.github.io/styleguide/jsguide.html).

## Equality

### `==` & `!=` 
So far, you’ve seen how you can use  `==`  and  `!=`  to compare numbers and strings for equality. However, if you use  `==`  and  `!=`  in situations where the data you’re comparing is mixed, it can lead to some interesting results. For example,

```
"1" == 1
```

> **Returns:**  true

and

```
0 == false
```

> **Returns:**  true

both evaluate to true. Why is that?

### Implicit Type Coercion

JavaScript is known as a  _loosely typed language_.

Basically, this means that when you’re writing JavaScript code, you do not need to specify data types. Instead, when your code is interpreted by the JavaScript engine it will automatically be converted into the "appropriate" data type. This is called  _implicit type coercion_  and you’ve already seen examples like this before when you tried to concatenate strings with numbers.

```
"julia" + 1
```

> **Returns:**  "julia1"

In this example, JavaScript takes the string  `"julia"`  and adds the number  `1`  to it resulting in the string  `"julia1"`. In other programming languages, this code probably would have returned an error, but in JavaScript the number  `1`  is converted into the string  `"1"`  and then is concatenated to the string  `"julia"`.

It’s behavior like this which makes JavaScript unique from other programming languages, but it can lead to some quirky behavior when doing operations and comparisons on mixed data types.

> **DEFINITION:** A **strongly typed language** is a programming language that is more likely to generate errors if data does not closely match an expected type. Because JavaScript is loosely typed, you don’t need to specify data types; however, this can lead to errors that are hard to diagnose due to implicit type coercion.

**Example of strongly typed programming language code**

```
int count = 1;
string name = "Julia";
double num = 1.2932;
float price = 2.99;
```

**Equivalent code in JavaScript**

```
// equivalent code in JavaScript
var count = 1; 
var name = "Julia";
var num = 1.2932;
var price = 2.99;
```

In the example below, JavaScript takes the string  `"1"`, converts it to  `true`, and compares it to the boolean  `true`.

```
"1" == true
```
When you use the `==` or `!=` operators, JavaScript first converts each value to the same type (if they’re not already the same type); this is why it's called "type coercion"! This is often not the behavior you want, and **it’s actually considered bad practice to use the  `==`  and  `!=`  operators when comparing values for equality**.

> **Returns:**  true

### Strict Equality: `===` & `!==`

Instead, in JavaScript it’s better to use  **strict equality**  to see if numbers, strings, or booleans, etc. are identical in  _type_  and  _value_  without doing the type conversion first. To perform a strict comparison, simply add an additional equals sign  `=`  to the end of the  `==`  and  `!=`  operators.

```
"1" === 1
```

> **Returns:**  false

This returns false because the string  `"1"`  is not the same type  _and_  value as the number  `1`.

```
0 === false
```

> **Returns:**  false

This returns false because the number  `0`  is not the same type  _and_  value as the boolean  `false`.

## Semicolons
One thing to take notice of in all the examples you've seen so far is the use of semicolons  `;`  at the end of each line. Semicolons make it clear where one statement ends and another begins. This is especially handy when multiple lines of code are written on the same line (which is valid JavaScript, but definitely not recommended!). For instance:

```
var totalAfterTax = 53.03 var tip = 8 // this is incorrect!

```

> **Uncaught SyntaxError:**  Unexpected token var

vs.

```
var totalAfterTax = 53.03; var tip = 8; // this is correct!
```

Not adding semicolons to the end of each line  _can_  cause bugs and errors in your programs. JavaScript does have ways to  _occasionally_  predict where semicolons  _should_  be, but just like how type coercion can result in some unexpected quirky behavior in JavaScript, it's good practice to not depend on it.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU5MTgxODkyXX0=
-->
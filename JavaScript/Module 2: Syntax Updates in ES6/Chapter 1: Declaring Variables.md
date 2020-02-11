# Module 1: Syntax Updates in ES6

## Chapter 1: Declaring Variables
- let & const
- template literals
- destructuring
- object literal shorthand

### Topic 1: Let & Const

#### Why `let` and `const` Added as Two New Ways to Declare Variables in JavaScript
  - Before the function is executed, all variables declared with `var` are hoisted to the top of the function scope, i.e. **Hoisting**.
	> **Hoisting** is a result of how JavaScript is interpreted by your browser. Essentially, before any JavaScript code is executed, all variables declared with `var` are "hoisted", which means they're raised to the top of the function scope.

  - Variables declared with `let` and `const` are only available within the block they're declared.

    Variables declared with `let` and `const` eliminate this specific issue of hoisting because they’re scoped **to the block**, not to the function. Previously, when you used `var`, variables were either scoped globally or locally to an entire function scope.

    If a variable is declared using `let` or `const` inside a block of code (denoted by curly braces `{ }`), then the variable is stuck in what is known as the temporal dead zone until the variable’s declaration is processed. This behaviour prevents variables from being accessed only until after they’ve been declared.

#### Rules for using let and const
`let` and `const` also have some other interesting properties.
- Variables declared with `let` can be reassigned, but can’t be redeclared in the same scope.
- Variables declared with `const` must be assigned an initial value, but can’t be redeclared in the same scope, and can’t be reassigned.

#### Use Cases
The big question is when should you use `let` and `const`? The general rule of thumb is as follows:

- use `let` when you plan to reassign new values to a variable, and
- use `const` when you don’t plan on reassigning new values to a variable.

**NOTE:** Since `const` is the strictest way to declare a variable, we suggest that you always declare variables with `const` because it'll make your code easier to reason about since you know the identifiers won't change throughout the lifetime of your program. If you find that you need to update a variable or change it, then go back and switch it from `const` to `let`.

#### What about var?
Is there any reason to use var anymore? Not really.

There are some arguments that can be made for using `var` in situations where you want to **globally** define variables, but this is often considered bad practice and should be avoided. From now on, we suggest ditching `var` in place of using `let` and `const`.

### Topic 2: Template Literals

#### Situation Prior to ES6: `+`/`concat()`
Prior to ES6, the old way to concatenate strings together was by using the string concatenation operator (`+`).
```
const student = {
  name: 'Richard Kalehoff',
  guardian: 'Mr. Kalehoff'
};

const teacher = {
  name: 'Mrs. Wilson',
  room: 'N231'
}

let message = student.name + ' please see ' + teacher.name + ' in ' + teacher.room + ' to pick up your report card.';
```
> **Returns:** Richard Kalehoff please see Mrs. Wilson in N231 to pick up your report card.

This works alright, but it gets more complicated when you need to build multi-line strings.
```
let note = teacher.name + ',\n\n' +
  'Please excuse ' + student.name + '.\n' +
  'He is recovering from the flu.\n\n' +

  'Thank you,\n' +
  student.guardian;
```
> **Returns:**
> Mrs. Wilson,
> 
> Please excuse Richard Kalehoff.
> He is recovering from the flu.
> 
> Thank you,
> Mr. Kalehoff

However, that’s changed with the introduction of *template literals* (previously referred to as "template strings" in development releases of ES6).
> **NOTE:** Newline characters: `\n`

> **NOTE:** As an alternative to using the string concatenation operator ( `+` ), you can use the String's `concat()` method, but both options are rather clunky for simulating true [string interpolation](https://en.wikipedia.org/wiki/String_interpolation).

#### Template Literals in ES6
Template literals are essentially string literals that include embedded expressions.

Denoted with backticks (`` ` ` ``) instead of single quotes (`' '`) or double quotes (`" "`), template literals can contain placeholders which are represented using ${expression}. This makes it much easier to build strings.

Here's the previous examples using template literals.
```
let message = `${student.name} please see ${teacher.name} in ${teacher.room} to pick up your report card.`;

```
>**Returns:** Richard Kalehoff please see Mrs. Wilson in N231 to pick up your report card.

By using template literals, you can drop the quotes along with the string concatenation operator. Also, you can reference the object's properties inside expressions.

...but what about the multi-line example from before?
```
let note = `${teacher.name} 

Please excuse ${student.name}.
He is recovering from the flu.

Thank you,
${student.guardian}`;
```

Here’s where template literals really shine. In the example above, the quotes and string concatenation operator have been dropped, as well as the newline characters ( `\n` ). That's because template literals also preserve newlines as part of the string!

> **TIP:** Embedded expressions inside template literals can do more than just reference variables. You can perform operations, call functions and use loops inside embedded expressions!

#### Example
```
/*
 * Programming Quiz: Build an HTML Fragment (1-2)
 */

const cheetah = {
    name: 'Cheetah',
    scientificName: 'Acinonyx jubatus',
    lifespan: '10-12 years',
    speed: '68-75 mph',
    diet: 'carnivore',
    summary: 'Fastest mammal on land, the cheetah can reach speeds of 60 or perhaps even 70 miles (97 or 113 kilometers) an hour over short distances. It usually chases its prey at only about half that speed, however. After a chase, a cheetah needs half an hour to catch its breath before it can eat.',
    fact: 'Cheetahs have “tear marks” that run from the inside corners of their eyes down to the outside edges of their mouth.'
};

// creates an animal trading card
function createAnimalTradingCardHTML(animal) {
    const cardHTML = `
    <div class="card">
        <h3 class="name">${cheetah.name}</h3>
        <img src="${cheetah.name}.jpg" alt="${cheetah.name}" class="picture">
        <div class="description">
            <p class="fact">"${cheetah.fact}"</p>
            <ul class="details">
                <li><span class="bold">Scientific Name</span>: ${cheetah.scientificName}</li>
                <li><span class="bold">Average Lifespan</span>: ${cheetah.lifespan}</li>
                <li><span class="bold">Average Speed</span>: ${cheetah.speed}</li>
                <li><span class="bold">Diet</span>: ${cheetah.diet}</li>
            </ul>
            <p class="brief">${cheetah.fact}</p>
        </div>
    </div>`;

    return cardHTML;
}

console.log(createAnimalTradingCardHTML(cheetah));
```

### Topic 3: Destructuring
In ES6, you can extract data from arrays and objects into distinct variables using destructuring.

This probably sounds like something you’ve done before, for example, look at the two code snippets below that extract data using pre-ES6 techniques:
- **Example 1: Extracting Values from an *Array***
```
const point = [10, 25, -34];

const x = point[0];
const y = point[1];
const z = point[2];

console.log(x, y, z);
```
> **Prints:** 10 25 -34

The example above shows extracting values from an **array**.

- **Example 2: Extracting Values from an *Object***
```
const gemstone = {
  type: 'quartz',
  color: 'rose',
  carat: 21.29
};

const type = gemstone.type;
const color = gemstone.color;
const carat = gemstone.carat;

console.log(type, color, carat);
```
> **Prints:** quartz rose 21.29

And this example shows extracting values from an **object**.

**In Summary**, both are pretty straightforward, however, neither of these examples are actually using destructuring.

So what exactly is **destructuring**?

#### Destructuring in ES6

**Destructuring** borrows inspiration from languages like [Perl](https://en.wikipedia.org/wiki/Perl) and [Python](https://en.wikipedia.org/wiki/Python_%28programming_language%29) by allowing you to specify the elements you want to extract from an array or object *on the left side of an assignment*. It sounds a little weird, but you can actually achieve the same result as before, but with much less code; and it's still easy to understand.

Let’s take a look at both examples rewritten using destructuring.

##### Destructuring values from an array

```
const point = [10, 25, -34];

const [x, y, z] = point;

console.log(x, y, z);

```

> **Prints:** 10 25 -34

In this example, the brackets `[ ]` represent the array being destructured and `x`, `y`, and `z` represent the variables where you want to store the values from the array. Notice how you don’t have to specify the indexes for where to extract the values from because the indexes are implied.

> **TIP:** You can also ignore values when destructuring arrays. For example, `const [x, , z] = point;` ignores the `y` coordinate and discards it.

##### Destructuring values from an object
```
const gemstone = {
  type: 'quartz',
  color: 'rose',
  carat: 21.29
};

const {type, color, carat} = gemstone;

console.log(type, color, carat);
```
> **Prints:** quartz rose 21.29

In this example, the curly braces `{ }` represent the object being destructured and `type`, `color`, and `carat` represent the variables where you want to store the properties from the object. Notice how you don’t have to specify the property from where to extract the values. Because `gemstone` has a property named `type`, the value is automatically stored in the `type` variable. Similarly, `gemstone` has a `color` property, so the value of `color` automatically gets stored in the `color` variable. And it's the same with `carat`.

> **TIP:** You can also specify the values you want to select when destructuring an object. For example, `let {color} = gemstone;` will only select the `color` property from the `gemstone` object.

### Topic 4: Object Literal Shorthand

A recurring trend in ES6 is to remove unnecessary repetition in your code. By removing unnecessary repetition, your code becomes easier to read and more concise. This trend continues with the introduction of new shorthand ways for initializing objects and adding methods to objects.

Let’s see what those look like.

#### Before
You’ve probably written code where an object is being initialized using the same property names as the variable names being assigned to them.

But just in case you haven’t, here’s an example.
```
let type = 'quartz';
let color = 'rose';
let carat = 21.29;

const gemstone = {
  type: type,
  color: color,
  carat: carat,
  calculateWorth: function() {
    // will calculate worth of gemstone based on type, color, and carat
  }
};
```
- Do you see the repetition? Doesn't `type: type`, `color: color`, and `carat:carat` seem redundant?
The good news is that you can remove those duplicate variables names from object properties _if_ the properties have the same name as the variables being assigned to them.

- In this example, an anonymous function is being assigned to the property `calculateWorth`, but is the function keyword really needed? In ES6, it’s not!

#### Now: Object Literal Shorthand in ES6
```
let gemstone = {
  type,
  color,
  carat,
  calculateWorth() { ... }
};
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NTA3NzUyMzBdfQ==
-->
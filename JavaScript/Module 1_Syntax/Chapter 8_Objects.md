# Chapter 8: Objects

[intro-to-javascript](https://cn.udacity.com/course/intro-to-javascript--ud803) ([backup](https://classroom.udacity.com/courses/ud803))

## What is an Object?
> Objects are a data structure in JavaScript that lets you tore data about a particular thing, and helps you keep track of hat that data by using a key.

## Object Literals

### Object-literal notation

```
var sister = {
  name: "Sarah", 
  age: 23,
  parents: [ "alice", "andy" ],
  siblings: ["julia"],
  favoriteColor: "purple",
  pets: true
};
```

The syntax you see above is called  **object-literal notation**. There are some important things you need to remember when you're structuring an object literal:

-   The "key" (representing a  **property**  or  **method**  name) and its "value" are separated from each other by a  **colon**`:`.
-   The  `key: value`  _pairs_  are separated from each other by  **commas**`,`.
-   The entire object is wrapped inside curly braces  `{ }`.

### Accessing Properties
And, kind of like how you can look up a word in the dictionary to find its definition, the  `key`  in a  `key:value`  pair allows you to look up a piece of information about an object. Here's are a couple examples of how you can retrieve information about my sister's parents using the object you created.

```
// two equivalent ways to use the key to return its value
sister["parents"] // returns [ "alice", "andy" ]
sister.parents // also returns ["alice", "andy"]
```

Using  `sister["parents"]`  is called  **bracket notation**  (because of the brackets!) and using  `sister.parents`  is called  **dot notation**  (because of the dot!).

[](https://classroom.udacity.com/courses/ud803/lessons/634eb53a-2f3f-47a3-9447-598090024758/concepts/cf57262b-5e91-4607-8e42-27949f7283c7#)

![A close-up image of an English dictionary](https://video.udacity-data.com/topher/2016/December/584eed0a_5510506796-e0aceddf28-o/5510506796-e0aceddf28-o.jpg)

Dictionary -  [Caleb Roenigk](https://www.flickr.com/photos/crdot/5510506796/in/photolist-9oWMFS-6mwLt2-6MpYQt-6bUfZa-7rTqj-8LVo5P-662Len-jQemaL-8xPfPp-7VHwy6-9zLxe-cywmx7-bZbDiy-8d1GNx-7vedzj-bwinBK-8Cxnmc-6bUiut-89pgc1-5nkeva-97tBaj-9Q74uJ-8X67Vx-a5okUi-vF2go-8sP2zd-9oLq73-7Chssi-6pLZoZ-8rR2E3-5EacGR-btHXgE-4WMBfS-ckMmcm-dqM1kk-bns32Q-cNEXES-9QznHQ-7UnEqR-7rTqi-5e5P7P-9TnBjv-8Ce2MH-2HFPiD-nZmwS-8jgD3D-hbdoo-8KdRLe-2HKZhd-8DTrVL)  -  [Creative Commons](https://creativecommons.org/licenses/by/2.0/)



## What about methods?

### Calling Methods
The sister object above contains a bunch of properties about my sister, but doesn't really say what my sister  _does_. For instance, let's say my sister likes to paint. You might have a  `paintPicture()`  method that returns "Sarah paints a picture!" whenever you call it. The syntax for this is pretty much exactly the same as how you defined the properties of the object. The only difference is, the  `value`  in the  `key:value`  pair will be a function.

```
var sister = {
  name: "Sarah",
  age: 23,
  parents: [ "alice", "andy" ],
  siblings: ["julia"],
  favoriteColor: "purple",
  pets: true,
  paintPicture: function() { return "Sarah paints!"; }
};

sister.paintPicture();
```

> **Returns**: "Sarah paints!"

and you can access the name of my sister by accessing the  `name`  property:

```
sister.name
```

> **Returns**: "Sarah"

## Naming Conventions

- key可以不用引号括起来，引起来可能会掩盖一些命名上的问题
- key不以数字开头，多个单词用camelCasing，而不是` `或`-`. (通常bracket notation不会报错，但dot notation会)

## Summary

Objects are one of the most important data structures in JavaScript. Get ready to see them everywhere!

They have properties (information about the object) and methods (functions or capabilities the object has). Objects are an incredibly powerful data type and you will see them all over the place when working with JavaScript, or any other object-oriented programming language.

### Object literals, methods, and properties

You can define objects using  **object-literal notation**:

```
var myObj = { 
  color: "orange",
  shape: "sphere",
  type: "food",
  eat: function() { return "yummy" }
};

myObj.eat(); // method
myObj.color; // property
```

### Naming conventions

Feel free to use upper and lowercase numbers and letters, but don't  _start_  your property name with a number. You don't need to wrap the string in quotes! If it's a multi-word property, use camel case. Don't use hyphens in your property names

```
var richard = {
  "1stSon": true;
  "loves-snow": true;
};

richard.1stSon // error
richard.loves-snow // error
```

### Exercise 1
#### Directions:

Create an object called  `facebookProfile`. The object should have 3 properties:

1.  your  `name`
2.  the number of  `friends`  you have, and
3.  an array of  `messages`  you've posted (as strings)

The object should also have 4 methods:

1.  `postMessage(message)`  - adds a new message string to the array
2.  `deleteMessage(index)`  - removes the message corresponding to the index provided
3.  `addFriend()`  - increases the friend count by 1
4.  `removeFriend()`  - decreases the friend count by 1

#### Your Code:
```
/*
 * Programming Quiz: Facebook Friends (7-5)
 */

// your code goes here
var facebookProfile = {
    name: "Dimple",
    friends: 3,
    messages: ["Awesome!", "Good news~", "So cuteee"],
    postMessage: function(message) {
        facebookProfile.messages.push(message);
    },
    deleteMessage: function(index) {
        facebookProfile.messages.splice(index-1,1);
    },
    addFriend: function() {
        facebookProfile.friends += 1;
    },
    removeFriend: function() {
        if (facebookProfile.friends >= 1) {
            facebookProfile.friends -= 1;
        }
    }
};
facebookProfile.addFriend();
facebookProfile.deleteMessage(2);
facebookProfile.postMessage("good job!");
console.log(facebookProfile.friends);
console.log(facebookProfile.messages);
```

### Exercise 2
Here is an array of donut objects.

```
var donuts = [
  { type: "Jelly", cost: 1.22 },
  { type: "Chocolate", cost: 2.45 },
  { type: "Cider", cost: 1.59 },
  { type: "Boston Cream", cost: 5.99 }
];

```

#### Directions:

Use the  `forEach()`  method to loop over the array and print out the following donut summaries using  `console.log`.

```
Jelly donuts cost $1.22 each
Chocolate donuts cost $2.45 each
Cider donuts cost $1.59 each
Boston Cream donuts cost $5.99 each
```

#### Your Code:
```
/*
 * Programming Quiz: Donuts Revisited (7-6)
 */

var donuts = [
    { type: "Jelly", cost: 1.22 },
    { type: "Chocolate", cost: 2.45 },
    { type: "Cider", cost: 1.59 },
    { type: "Boston Cream", cost: 5.99 }
];

// your code goes here
donuts.forEach(function(donut) {
    console.log(donut.type + " donuts cost $" + donut.cost + " each");
})
```

**Solution 2**
```
/*
 * Programming Quiz: Donuts Revisited (7-6)
 */

var donuts = [
    { type: "Jelly", cost: 1.22 },
    { type: "Chocolate", cost: 2.45 },
    { type: "Cider", cost: 1.59 },
    { type: "Boston Cream", cost: 5.99 }
];

// your code goes here
for(var i = 0; i < donuts.length; i++) {
    console.log(donuts[i].type + " donuts cost $" + donuts[i].cost + " each");
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA3NzcxOTE5MCw3MzA5OTgxMTZdfQ==
-->
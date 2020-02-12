# Module 2: The DOM

## Chapter 3: Selecting Page Elements

 1. Select Page Element With CSS
 2. Select Page Element By ID
 3. Select Multiple Elements
	- Accessing Elements By Their Class
	- Accessing Elements By Their Tag
 4. More Ways to Access Elements
	- jQuery
	- The querySelector Method
	- The querySelectorAll Method

---
### Topic 1: Select Page Element With CSS
If you struggled a little bit with this section, perhaps you should do a quick review of CSS by reviewing the [HTML and CSS course](https://www.udacity.com/course/intro-to-html-and-css--ud001).

### Topic 2: Select Page Element By ID

#### Know-How
Let's take a look at how we can use JavaScript and the DOM to gain access to specific elements using their ID attribute.

Remember the `document` object from the previous section? Well, we're going to start using it! Remember the `document` object is an object, just like a JavaScript object. This means it has key/value pairs. Some of the values are just pieces of data, while others are functions (also known as **methods**!) that provide some type of functionality. The first DOM method that we'll be looking at is the `.getElementById()` method:

```
document.getElementById();
```

If we ran the code above in the console, we wouldn't get anything, because we did not tell it the ID of any element to get! We need to pass a string to `.getElementById()` of the ID of the element that we want it to find and subsequently return to us:

```
document.getElementById('footer');
```

One thing to notice right off the bat, is that we're passing `'footer'`, not `'#footer'`. It already knows that it's searching for an ID (its name _is_ "getElementById", for a reason!).

If you'd like to read more about this method, check out its documentation page on MDN: [https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById)

#### Selecting By ID Recap

In this section, we learned how to select a DOM element by its ID:

-   `.getElementById()`

There are a couple of important things to keep in mind about this method:

-   it is called on the `document` object
-   it returns a _single_ item

```
// select the element with the ID "callout"
document.getElementById('callout');

```

#### Further Research

-   [.getElementById()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById) on MDN


### Topic 3: Select Multiple Elements

As I'm sure you remember from learning both HTML structure and CSS styling, an ID should be _unique_ - meaning two or more elements should never have the same ID. Since IDs are unique, and since there will be only one element in the HTML with that ID, `document.getElementById()` will only ever return at most one element. So how would we select multiple DOM elements?

The next two DOM methods that we'll be looking at that both return multiple elements are:

-   `.getElementsByClassName()`
-   `.getElementsByTagName()`

#### Beware of the S!

I know we haven't looked at `.getElementsByTagName()` just yet, but there's something different about `.getElementById()` compared with both `.getElementsByClassName()` and `.getElementsByTagName()` that I want to point out because it can be easy to miss; both `.getElementsByClassName()` and `.getElementsByTagName()` have an extra "s" in their name.

The method's name is `.getElementsByClassName()`, not `.getElementByClassName()`. Notice the word right in the middle, it's "Elements" not "Element". If you think about it, this actually makes a lot of sense! Since both `.getElementsByClassName()` and `.getElementsByTagName()` could return multiple items, their method names tell us that directly. Now compare this with `.getElementById()` that will only ever return at most _one_ element. Its name has the singular "Element" in it.

I just wanted to point this out because I've been bitten by that missing "s" many-a-time when running code like:

```
document.getElementByClassName('highlight-spanned');
```

This code above will _not_ work, because there is no DOM method `.getElementByClassName()` (with singular "Element").

#### Topic 3.1: Accessing Elements By Their Class

The first method we'll look at is `.getElementsByClassName()`:

```
document.getElementsByClassName();
```

Similarly to `.getElementById()`, if we ran the code above in the console, we wouldn't get anything, because we did not tell it the class to search for! Also just like `.getElementById()`, `.getElementsByClassName()` is expecting that we call it with a string of the class we want it to search for/return:

```
document.getElementsByClassName('brand-color');
```

If you'd like to read more about this method, check out its documentation page on MDN: [https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName)

#### Topic 3.2: Accessing Elements By Their Tag

After looking at both `.getElementById()` and `.getElementsByClassName()`, the new `.getElementsByTagName()` method should seem quite easy on the eyes:

```
document.getElementsByTagName('p');
```

#### What's Returned?
We just saw that `.getElementsByClassName()` returns an array-like data structure of elements. But what exactly _is_ an element?

In the next section, we'll take the plunge and look at Elements and Nodes.

#### Recap

In this section, we learned two ways to select multiple DOM elements:

-   `.getElementsByClassName()`
-   `.getElementsByTagName()`

There are a few important things to keep in mind about these two methods:

-   both methods use the `document` object
-   both return multiple items
-   the list that's returned is not an array

```
// select all elements that have the class "accent-color"
document.getElementsByClassName('accent-color');

// select all "span" elements
document.getElementsByTagName('span');

```

#### Further Research

-   [.getElementsByClassName()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName) on MDN
-   [.getElementsByTagName()](https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagName) on MDN


### Topic 4: More Ways to Access Elements

#### Topic 4.1: jQuery 
We've been looking at the:

-   `.getElementById()`
-   `.getElementsByClassName()`
-   and `.getElementsByTagName()`

Now these DOM methods are standardized. However, not all browsers support every standard. They do _now_, for these three methods, but there are hundreds of other methods with varying levels of support.

That's why almost every method on MDN has a Browser compatibility table that lists when each browser started supporting that specific method.

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/2e6da026-d11e-48b8-956e-e3e1890c5819/modules/f7eca45d-0cca-481f-a280-a835629b4be4/lessons/74c2a096-61db-4302-9d65-6b7fa9b8c329/concepts/eee59c35-d033-4714-b331-b042b7a36564#)

![A Screenshot showing the Browser compatibility table for the `.getElementsByClassName()` method, Chrome, Edge, Opera, and Safari are marked as Yes. Firefox is 3.0 and IE is 9.0](https://video.udacity-data.com/topher/2017/December/5a22d8c5_ud117-l1-browser-compatibility-table/ud117-l1-browser-compatibility-table.jpg)

_The Browser compatibility table for the `.getElementsByClassName()` method._

Thankfully, all browsers have pretty much aligned to support the official standard.

However, back in the day, that wasn't the case. You had to write different code to perform the same action in different browsers. Then you had to write code to check which browser you were in to run the correct code for that browser. Let me tell you, it was a bit of a nightmare.

Several JavaScript libraries came along to help mitigate these issues. Let's take a brief look at the [jQuery library](https://jquery.com/).


#### Topic 4.2: The querySelector Method
We already reviewed this in a previous section, but let's recap it one more time!

```
#header {
    color: 'red';
}

.header {
    color: 'red';
}

header {
    color: 'red';
}
```

Each one of these sets the color to red. The only difference is in the selector; selecting by ID, selecting by class, and selecting by tag. Got it? Good!

You've already learned the DOM methods to select by ID, class, and tag, too:

-   `.document.getElementById()`
-   `.document.getElementsByClassName()`
-   `.document.getElementsByTagName()`

Three different methods that do almost the exact same thing. Wouldn't it be awesome if there were a way to do element selecting similar to how CSS does it?

Wait for it - there is **The querySelector Method**

We can use the `.querySelector()` method to select elements just like we do with CSS. We use the `.querySelector()` method and pass it a string that's just like a CSS selector:

```
// find and return the element with an ID of "header"
document.querySelector('#header');

// find and return the first element with the class "header"
document.querySelector('.header');

// find and return the first <header> element
document.querySelector('header');

```

Check out the `.querySelector()` method on MDN: [https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)

> ##### ⚠️ `.querySelector()` Returns A Single Element ⚠️

> I want to point out one potentially tricky thing - the `.querySelector()` method only returns _one_ element. This makes sense if you use it to search for an element by ID. However, even though `.getElementsByClassName()` and `.getElementsByTagName()` both return a list of multiple elements, using `.querySelector()` with a class selector or a tag selector will still only return the _first_ item it finds.

#### Topic 4.3: The querySelectorAll Method

The `.querySelector()` method returns only _one_ element from the DOM (if it exists). However, there are definitely times when you will want to get a list of all elements with a certain class or all of one type of element (e.g. all `<tr>` tags). We can use the `.querySelectorAll()` method to do this!

```
// find and return a list of elements with the class "header"
document.querySelectorAll('.header');

// find and return a list of <header> elements
document.querySelectorAll('header');
```
It's important to remember that what's returned is not an array, is actually a special list called "NodeList". Because it's not actually an array, we can't use the array method `.map` to loop over its items. Instead, we can just use a `for` loop.

Here's the `.querySelectorAll()` method on MDN: [https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)

#### Recap

In this section, we took a brief look the history of browser support for standard DOM methods, the rise of the jQuery library, and how jQuery's success brought about new DOM methods. The new DOM methods we looked at are

-   `.querySelector()` - returns a single element
-   `.querySelectorAll()` - returns a list of elements

```
// find and return the element with an ID of "header"
document.querySelector('#header');

// find and return a list of elements with the class "header"
document.querySelectorAll('.header');
```

We also took a brief look that the list returned by `.querySelectorAll()` is a NodeList. We saw that it is possible to loop over a NodeList with either its `.forEach()` method, or the humble `for` loop:

```
const allHeaders = document.querySelectorAll('header');

for(let i = 0; i < allHeaders.length; i++){
    console.dir(allHeaders[i]);
}

```

#### Further Research

-   [jQuery website](https://jquery.com/)
-   [.querySelector() method on MDN](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
-   [.querySelectorAll() method on MDN](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)
-   [NodeList on MDN](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAyMjAxNDg0OF19
-->
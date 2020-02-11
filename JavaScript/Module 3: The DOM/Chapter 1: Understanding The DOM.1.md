# Module 2: The DOM

## Chapter 1: Understanding The DOM

 1. Introduction to the DOM
 2. The DOM Recap
 3. Further Research

---

### Topic 1: Introduction to the DOM

In this section, we'll look at the Document Object Model - otherwise known as the DOM.

The words "the DOM" are used all over developer documentation sites and tutorials on writing interactive JavaScript code. But what is it? Perhaps you've used even used the DOM and still aren't quite sure what it is. Is it the browser? Is it a special part of JavaScript?

#### How we get from the HTML source to what we see in the browser
The HTML specification contains a set of rules...

 1. **characters** >> **tags** HTML is received
 2. **tokens** HTML tags are converted to tokens
 3. **nodes** tokens are converted to Nodes
 4. **DOM** Nodes are converted to the DOM

When you request a website, no matter what backend language is powering that website, it will respond with HTML. The browser receives a stream of HTML. The bytes are run through a complicated (but fully documented) parsing process that determines the different characters (e.g. the start tag character `<`, an attribute like `href`, a closing angle bracket like `>`). After parsing has occurred, a process called **tokenization**. Tokenization takes one character at a time and builds up **tokens**. The tokens are:

-   DOCTYPE
-   start tag
-   end tag
-   comment
-   character
-   end-of-file

Let's take a break for a second. At this state, the browser has received the bytes that've been sent by a server. The browser has converted the bytes to tags and has read through the tags to create a list of tokens.

This list of tokens then goes through the tree construction stage. The output of this stage is a tree-like structure - this is the DOM!

I want to point out two important quotes that Illya said in the video:

> a tree structure that captures the content and properties of the HTML and all the relationships between the nodes

> the DOM is the full, parsed representation of the HTML

So the DOM is a model (representation) of the relationships and attributes of the HTML document that was received. Remember that DOM stands for "Document Object Model". Something that I've found to be true as I've been learning is that to break something down, just read the thing backwards:

Document Object Model

...would become…

Object Model of the Document!

#### The `document` object

**Remember that a JavaScript object is a tree-like structure that has properties and values. So the DOM can be accessed using a special object provided by the browser: `document`**

Try this:

1.  open the console on this page
2.  type out the word `document`
    -   careful not to declare it (`const document`)
    -   careful not to wrap it in quotes (`"document"`)
3.  press enter

![A Screenshot viewing the `document` object in the DevTools' Console pane.](https://video.udacity-data.com/topher/2017/December/5a22336a_ud117-l1-document-object-in-console/ud117-l1-document-object-in-console.jpg)

The `document` object is provided by the browser and is a representation of the HTML document. This object is _not_ provided by the JavaScript language. ECMAScript is the language specification that JavaScript is based on, and it only references the document object model in one place, in its "Global Object" section:

> In addition to the properties defined in this specification the global object may have additional host defined properties. This may include a property whose value is the global object itself; for example, in the HTML document object model the window property of the global object is the global object itself. ([source](https://www.ecma-international.org/ecma-262/#sec-global-object))

Basically, this says that the `document` object is not part of JavaScript, but is expected to _already exist_ and be freely accessible to JavaScript code.

The DOM is standardized by the W3C. There are a number of specifications that make up the DOM, here are few:

-   Core Specification
-   Events Specification
-   Style Specification
-   Validation Specification
-   Load and Save Specification

To see the full list of DOM specs, check out the standard at: [https://www.w3.org/standards/techs/dom#w3c_all](https://www.w3.org/standards/techs/dom#w3c_all)

### Topic 2: The DOM Recap

The DOM stands for "Document Object Model" and is a tree-like structure that is a representation of the HTML document, the relationship between elements, and contains the content and properties of the elements.

The DOM is _not_:

-   part of the JavaScript language

The DOM is:

-   constructed from the browser
-   is globally accessible by JavaScript code using the `document` object

The DOM is used all of the time and is what we'll be using throughout this course!

### Topic 3: Further Research

-   [DOM Introduction](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
-   [Section 8.2 Parsing HTML documents](https://www.w3.org/TR/html5/syntax.html#parsing) from the W3C's HTML Documentation
-   [DOM Specification](https://www.w3.org/standards/techs/dom#w3c_all) on W3C
-   [HTML Document Object Model mentioned in the ECMAScript Specification](https://www.ecma-international.org/ecma-262/#sec-global-object) - the language specification used by JavaScript

- [HTTP 和 Web 服务器](https://cn.udacity.com/course/http-web-servers--ud303)


HTTP 是网络的基本协议。在这门课程中，使用 Python 和命令行探索它的原理。



- [Shell 讲习班](https://classroom.udacity.com/courses/ud206)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1NDY1NTc3OTFdfQ==
-->
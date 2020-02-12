# Module 2: The DOM

## Chapter 2: Nodes, Elements, and Interfaces

 1. Node Interface
 2. Element Interface
 3. Further Research

---

### Topic 1: Node Interface
#### Node with a capital N *vs* node with a lowercase n

Node with a capital N is like a class, which is like the blueprint for a building and includes...

 - properties (data about the building)
	 - the color of the building
	 - number of the doors
	 - number of the windows
 - methods (functionalities of the building)
	 - alarm system
	 - sprinkler system
	 - number of the windows

Let's say that this blueprint is a model for lots of real buildings.
Another word we can use instead of blueprint is **interface**.
An interface tells us the properties and methods that are applied to the individual items.

> #### ⚠️ Interface *vs* User Interface ⚠️
> 
> The word "interface" might be an unclear word right now, and that's ok. I do want to make sure that you're not connecting this "interface" with a _user interface_ (UI) or a graphical user interface (GUI).
> 
> Our use of "interface" is not related to either a UI or a GUI. Our use of "interface" is a technical, computer science word for a list of properties and methods that are inherited.


#### Summary
Node (with a capital "N"!) is a blueprint that contains information about all of the properties and methods for real nodes (with a lowercase "n"!). If you're not used to them, the words "**interface**", "**property**", and "**method**" can be kind of cryptic at first. Just remember that:

-   interface = blueprint
-   properties = data
-   methods = functionality

Let's check out Node on MDN: [Node Interface on MDN](https://developer.mozilla.org/en-US/docs/Web/API/Node)

So the Node Interface is a blueprint for all of the properties (data) and methods (functionality) that every real node has after it's been created. Now, the Node Interface has a lot of properties and methods, but it's not very _specific_...I mean, what _is_ a node???

Just like "blueprint for a Building" is not as specific as "blueprint for a house" or "blueprint for a skyscraper". These are more-specific blueprints. And these more-specific blueprints would probably have their own properties and methods that are specific to _just_ houses or _just_ skyscrapers.

This brings us to the "Element Interface".

### Topic 2: Element Interface

Just like the Node Interface, the Element Interface is a blueprint for creating elements: [Element Interface on MDN](https://developer.mozilla.org/en-US/docs/Web/API/Element)

One really important thing about the Element Interface is that it is a descendant of the Node Interface.

![A diagram showing an Element with an arrow pointing to Node, and Node with an arrow pointing to EventTarget](https://video.udacity-data.com/topher/2017/December/5a22d197_ud117-l1-interface-chain/ud117-l1-interface-chain.jpg)

_Element points to its parent, Node._

Since Element is pointing at Node, this indicates that the Element Interface inherits all of the Node Interface's properties and methods. This means that any element (lowercase "e"!) that was created from the Element Interface is _also_ a descendent from the Node Interface...which means the element (lowercase "e"!) is also a node (lowercase "n"!).

### Topic 3: Further Research
Do you remember the `.getElementsByClassName()` method on the `document` object that we looked at previously? While reviewing the Element interface, you might've noticed that it _also_ has a `.getElementsByClassName()` method! The Element Interface inherits from the Node Interface, not the Document Interface (yep, there's a Document Interface!). The Element Interface has its own `.getElementsByClassName()` that does the exact same thing as the one on the `document` object.

This means that you can use the `document` object to select an element, _then_ you can call `.getElementsByClassName()` on that element to receive a list of elements with the class name that are descendents of that specific element!

```
// selects the DOM element with an ID of "sidebar"
const sidebarElement = document.getElementById('sidebar');

// searches within the "sidebar" element for any elements with a class of "sub-heading"
const subHeadingList = sidebarElement.getElementsByClassName('sub-heading
```

To check out all of the different interfaces, check here: [Web API Interfaces](https://developer.mozilla.org/en-US/docs/Web/API)

#### Reference
-   [Node Interface](https://developer.mozilla.org/en-US/docs/Web/API/Node)
-   [Element Interface](https://developer.mozilla.org/en-US/docs/Web/API/Element)
-   [list of Web API Interfaces](https://developer.mozilla.org/en-US/docs/Web/API)

### Recap

Hopefully this was an enlightening lesson on a number of fronts! You learned about interfaces, properties, and methods; an interface is like a blueprint, properties are like bits of information or data, and methods are functionality.

We also looked at a couple of specific interfaces:

-   Node Interface
-   Element Interface

We saw that both of these interfaces have properties and methods. We also saw how the Element Interface inherits all of the properties and methods from the Node interface.
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzA0NTA2Nzg2XX0=
-->
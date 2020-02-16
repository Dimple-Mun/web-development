# Chapter 1: What is JavaScript

[intro-to-javascript](https://cn.udacity.com/course/intro-to-javascript--ud803) ([backup](https://classroom.udacity.com/courses/ud803))

## History of JavaScript

(video)

> **TIP**: HTML and CSS are **markup languages**. Markup languages are used to describe and define elements within a document. JavaScript is a **programming language**. Programming languages are used to communicate instructions to a machine. Programming languages can be used to control the behavior of a machine and to express algorithms.

## The JavaScript Console

[Chrome Dev Tools Keyboard Shortcuts](https://developers.google.com/web/tools/chrome-devtools/shortcuts)

## Developer Tools on Different Browsers

Did you know, every modern web browser includes its own set of developer tools?

If you didn't, that's okay. Developer tools aren't always the easiest thing to find in your browser. So, we've decided to help you out by creating this guide to developer tools!

### Instructions

-   [Google Chrome](https://classroom.udacity.com/courses/ud803/lessons/e98aae00-9563-4fca-b91c-a4e79ca79c27/concepts/74478058180923#google)
-   [Mozilla Firefox](https://classroom.udacity.com/courses/ud803/lessons/e98aae00-9563-4fca-b91c-a4e79ca79c27/concepts/74478058180923#firefox)
-   [Internet Explorer](https://classroom.udacity.com/courses/ud803/lessons/e98aae00-9563-4fca-b91c-a4e79ca79c27/concepts/74478058180923#explorer)
-   [Microsoft Edge](https://classroom.udacity.com/courses/ud803/lessons/e98aae00-9563-4fca-b91c-a4e79ca79c27/concepts/74478058180923#edge)
-   [Safari](https://classroom.udacity.com/courses/ud803/lessons/e98aae00-9563-4fca-b91c-a4e79ca79c27/concepts/74478058180923#safari)
-   [Opera](https://classroom.udacity.com/courses/ud803/lessons/e98aae00-9563-4fca-b91c-a4e79ca79c27/concepts/74478058180923#opera)

### Google Chrome

The Chrome DevTools are a set of web authoring and debugging tools built into Google Chrome. Use the DevTools to iterate, debug and profile your site.  [Learn more about Chrome DevTools here](https://developers.google.com/web/tools/chrome-devtools/).

To open Chrome DevTools, either right-click on any page element and select  `Inspect`  or open the Chrome settings menu in the top-right corner of your browser window and select  `More Tools > Developer Tools`. Alternatively, you can use the shortcuts:

-   `Command + Option + i`  (Mac)
-   `Ctrl + Shift + i`  (Windows/Linux).

### Mozilla Firefox

Firefox Developer Tools allow you to examine, edit, and debug HTML, CSS, and JavaScript on the desktop and on mobile. Also, you can download a version of of Firefox called Firefox Developer Edition that is tailored for developers, featuring the latest Firefox features and experimental developer tools.  [Learn more about Mozilla Firefox DevTools here](https://developer.mozilla.org/en-US/docs/Tools).

To open Firefox Developer Tools, either right-click on any page element and select  `Inspect Element`  or open the Firefox settings menu in the top-right corner of your browser window and select  `Developer`. Alternatively, you can use the shortcuts:

-   `Command + Option + i`  (Mac)
-   `Ctrl + Shift + i`  (Windows/Linux).

### Internet Explorer

If you use Internet Explorer, then you can access F12 developer tools by simply pressing  `F12`. The features vary between versions, but starting at Internet Explorer 8 remain pretty consistent. Below, we've linked to documentation for each version, but if you've upgraded to Microsoft Edge, then check the next section.

-   [Internet Explorer 8](https://msdn.microsoft.com/en-us/library/dd565628.aspx)
-   [Internet Explorer 9](https://msdn.microsoft.com/en-us/library/gg589512.aspx)
-   [Internet Explorer 10](https://msdn.microsoft.com/en-us/library/hh673549.aspx)
-   [Internet Explorer 11](https://msdn.microsoft.com/en-us/library/bg182636.aspx)

### Microsoft Edge

Microsoft Edge introduces great new improvements to the F12 developer tools seen in Internet Explorer. The new tools are built in TypeScript, and are always running, so no reloads are required. In addition, F12 developer tools documentation is now fully available on  [GitHub](https://github.com/MicrosoftDocs/edge-developer).

Just like Internet Explorer, to open developer tools in Microsoft Edge simply press  `F12`.

[Learn more about Microsoft Edge DevTools here](https://dev.windows.com/en-us/microsoft-edge/platform/documentation/f12-devtools-guide/).

### Safari

For any Mac users, Safari includes Web Inspector, a powerful tool that makes it easy to modify, debug, and optimize a website for peak performance and compatibility on both platforms.  [Learn more about Safari Web Inspector here](https://developer.apple.com/safari/tools/).

To access Safari's Web Development Tools, enable the Develop menu in Safari’s Advanced preferences.  Once enabled, you can right-click on any page element and select  `Inspect Element`  to open Web Development Tools or use the shortcut  `Command + Option + i`.

### Opera

Fast, lean and powerful, Opera comes pre-packed with a fully-featured suite of developer tools. Named Opera Dragonfly, it is designed to make your job easier.  [Learn more about Opera Dragonfly here](http://www.opera.com/dragonfly/).

Launch Opera Dragonfly with the following keyboard shortcuts:

-   `Command + Option + i`  (Mac)
-   `Ctrl + Shift + i`  (Windows/Linux).

Alternatively, you can target a specific element by right-clicking in the page and selecting  `Inspect Element`.

## Command: `console.log`

`console.log`  is used to display content to the  **JavaScript console**. Run the following code in the console:

```
console.log("hiya friend!");

```

> **Prints:**  "hiya friend!"

Congratulations! You performed the  `log`  action on the debugging  `console`.

The message you’ve logged is "hiya friend!".  `hiya friend!`  is a  **string**  (a sequence of characters).

### Optional demo example

Let’s use  `console.log`  to do something a little more interesting. Here’s a block of JavaScript code that loops through the numbers 0 through 9 and prints them out to the console:

```
for (var i = 0; i < 10; i++) {
  console.log(i);
}

```

> **Prints**:  
> 0  
> 1  
> 2  
> 3  
> 4  
> 5  
> 6  
> 7  
> 8  
> 9  

This is called a  **loop**.

Based on this loop's settings, any code written inside the curly brackets  `{...}`  will be repeated 10 times. In this case,  `console.log`  is printing out the value of  `i`  each time the loop runs. Don't worry if you're not sure about what the syntax means at this point. You will learn more about how and when to use loops later in this course.

## JavaScript Demo

So you saw how to use  `console.log`  to print a message to the JavaScript console. Now, let’s see how you can use the console as a sandbox to test a new line of JavaScript in the browser.

Open  [the following site](https://daringfireball.net/projects/markdown/)  in a new tab and in that tab also open up developer tools. Then paste the following code:

```
document.getElementsByTagName("h1")[0].style.color = "#ff0000";
```
Styling elements on the page is great, but you could also do that by just modifying the CSS. What makes JavaScript so special in this case? Refresh the page, then paste this line of code in the JavaScript console.

```
document.body.addEventListener('click', function () {
     var myParent = document.getElementsByTagName("h1")[0]; 
     var myImage = document.createElement("img");
     myImage.src = 'https://thecatapi.com/api/images/get?format=src&type=gif';
     myParent.appendChild(myImage);
     myImage.style.marginLeft = "160px";
});

```

If you’re confused because nothing happened. Don’t worry. Click somewhere on the page to see the effect. You can refresh the page to return the page its original state.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIyNzM2MDE2M119
-->
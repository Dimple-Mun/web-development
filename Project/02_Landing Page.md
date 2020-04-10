> JavaScript and The DOM

# Project Summary

**落地页**

This project aims to give you real-world scenarios of manipulating the DOM. The functionality you will be using serves two purposes: to prepare you for appending dynamically added data to the DOM, and to show you how javascript can improve the usability of an otherwise static site. This project barely touches the surface of what is possible, but it does use some incredibly common events, methods, and logic.

For this project, refactor and test as much as possible while you are building. You should figure for every piece of functionality you add, you will likely spend just as much time testing and refactoring your code. If it takes you 3 hours to figure out the logic, it should likely take you another 3 hours determining that you wrote the best code possible. As your skills improve, this process will feel more natural. Make sure to remove any debugging code from your final submission.

## What You Will Build

You will be building a multi-section landing page. Often times, we don’t know how much content will be added to a page through a CMS or an API. To circumvent this problem, we can dynamically add the content to the page. We will be demonstrating this with the navigation menu. Additionally, dynamically building the navigation is a great precursor to understanding the virtual DOM which you will experience when you begin working with JavaScript frameworks.

To improve the user experience, the section actively being viewed should be differentiated in some way. Additionally, when a user clicks on a navigation item, the item should scroll you to the appropriate section rather than giving you the default jump.

This may not sound like a lot, but there are a fair amount of moving pieces that rely on each other to work. You’ll need to plan out the logic of what you are trying to accomplish before you begin developing. If you find this process to be quick, there’s a list of additional functionality that you can add that all strive to improve the users’ experience.

## What will I learn?

The landing page presents the first opportunity to fully combine your skills in HTML, CSS, and JavaScript into a large project. Aside from solidifying your skills with these three technologies, you’ll discover how best to combine them in a complex application.

The following are just some of the questions that you’ll experience along the way:

-   What’s the ideal workflow?
-   How many files do I need?
-   Do I modify the HTML first or the CSS?
-   How many JavaScript functions do I need?
-   Should my function be this many lines of code?
-   Is readability or performance more important?

There’s no single correct answer to each question. While building this project, working with peers, and getting feedback from the project reviewer -- you will naturally develop your own answers to these questions!

# Getting Started

## Introduction

This project requires you to build a multi-section landing page, with a dynamically updating navigational menu based on the amount of content that is added to the page.

## Project Rubric

Your project will be evaluated by a Udacity code reviewer according to the Landing Page  [project rubric](https://review.udacity.com/#!/rubrics/2658/view). Please review for detailed project requirements.

## Get the Starter Code

If you'd like to start from scratch without any files, you are encouraged to do so! You learn the most by developing on your own! But, it can be a bit challenging having to start from scratch, so we do provide a starter project (i.e., a "skeleton") to use.

You can download the starter code  [here](https://github.com/udacity/fend/tree/refresh-2019)  by cloning the specific branch 'refresh-2019'.

The starter code has a static, non-interactive version of the project so you can get a jump-start on development!

## JavaScript and the DOM

Great! You now have the starter code. Before moving forward, make sure you are comfortable with the content from the JavaScript and the DOM course. Ask yourself:

-   What is the  [Document](https://developer.mozilla.org/en-US/docs/Web/API/Document)?
-   What are  [events](https://developer.mozilla.org/en-US/docs/Web/API/Event)?
    -   How do we  [listen for them](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)?
    -   How does  **event delegation**  help us avoid too many events?
    -   Check  **Working with Browser Events**  in JavaScript and the DOM for a refresher if needed
-   How can we access elements with the following two methods? What are the differences between them?
    -   [querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
    -   [querySelectorAll()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)
-   How do you use  [getElementbyId()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById)  to select a DOM element by its  `id`?
-   We can also access elements with  [getElementsByClassName()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName). What does this method return, and how do you use it?
-   How do you use the  [className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)  property? What does it return, and why would it be useful?
-   What are the different methods for  [classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList#Methods)?
    -   Hint: the  `add()`,  `remove()`, and  `toggle()`  methods look particularly useful...
-   Every element has an  [innerHTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML)  property that represents the markup of the element's content. How can you leverage this property to  _get_  and  _set_  content?

# Development Strategy

For this project, you will be writing most of your code in  **js/app.js**. Note that it's very important that you  _plan your project_  before you start writing any code! Break your project down into  _small_  pieces of work and strategize your approach to each one. With these bite-sized amounts, it'll be easier to debug and fix any issues that appear.

Feel free to implement your own design workflow, but if you get stuck -- here is a walkthrough to get you up and running!

1.  **Start by linking your app.js**. where should this file go based on your present knowledge? We’ll test some other locations later.
2.  **Build out your HTML and at least 3 content sections**. The rest of your functionality relies on these sections.
    -   Take a quick look at all the HTML elements in  **index.html**. Note the values for their  `id`,  `class`, and  `data`  attributes. To manipulate the DOM, you'll be using many of the tools and methods you've learned on these elements (and on those that you will create).
        -   For a refresher on the data attribute, visit  [here](https://www.w3schools.com/tags/att_data-.asp).
    -   Which data structure can you use to store these sections? This data structure can represent all sections for your page, so it might be a good idea to save it to a variable.
    -   How you would iterate (i.e., loop) over this data structure?
    -   Think about how you can create, say, an  _unordered list_  (i.e., bulleted list) in HTML from this structure, and where you be placing that list.
    -   Think about how you’ll test whether a section is in the viewport.
    -   What actions are you performing that will cause interactivity with the DOM?
3.  **Build the navigation menu**. This will dynamically create a navigation menu based on the sections of the page. This can be a particularly useful trick when you begin working with content management systems or APIs when you are uncertain of the items will be.
    -   Are you listening for an event for the navigation to build?
    -   Where are you placing the navigation?
    -   Where is the text for each navigation item coming from and where are you anchoring to?
    -   How are you going to add each navigation item to your menu? (Hint: there are several ways to do this. Do some research to figure out which makes the most sense for your situation. Performance? Clarity?).
4.  **Add functionality to distinguish the section in view**. While navigating through the page, the section that is active in the viewport/closest to the top should be distinguished from the other sections.
    -   Are you listening for an event for sections to become active?
    -   How are you going to test which section should be highlighted?
    -   How can we use  `classList`  [methods](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList#Methods)  to change the CSS being displayed? What about removing that CSS?
    -   Check the HTML and CSS files to ensure that what you chose is updated in the other locations.
5.  **Add the functionality to scroll to sections**. Clicking on a navigation item should scroll to the appropriate section of the page.
    -   Which event are you listening for (hint: you were just reading it)?
    -   There is a default event occurring that we need to stop. How?
    -   If you don’t recall how HTML page anchors work,  [read more](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#Examples)  to figure out which variables you should set.
    -   There are several javascript methods for scrolling. Which seems like it may be the most simple?
6.  **REFACTOR**. At this point, your code should be working properly. Ideally, refactoring happens while you are developing, but as a new developer, you often don’t have the whole picture in your head to be able to do so properly. Let’s clean the project up.
    -   Have you run your code through a linter? We request you still follow Udacity standards when the code is complete, but running it through an  [eslinter](https://eslint.org/demo)  is going to help you get started in refactoring.
    -   Are you using ES6 const and let?
    -   Are all your functions using ES6 arrow functions?
    -   Is your code DRY? Are there any pieces that would be better served as a helper function to avoid duplication?
    -   How is your code structured? Have you created functions for the main functionality with properly scoped variables? Starting out it’s likely that you will have a globally scoped variables on occasion until you learn more about closures and design patterns. But placing your code into functions is a great way to make your code more readable and a way to avoid globally scoped variables.
    -   Are you using the best method for your iterations?
7.  **Add additional sections to your HTML document**. See how the navigation builds.
8.  **Test the performance**. The performance of your page can be affected by how you write your javascript as well as where you load your javascript.
    -   Test loading the javascript in the head vs at the end of the body. What issues arise? Is there a way to still load in the head without breaking the page? What is the performance like compared to loading at the end of the body?
9.  **Suggested**:
    -   Add an active state to your navigation items when a section is in the viewport.
    -   Hide fixed navigation bar while not scrolling (it should still be present on page load).
        -   Hint: setTimeout can be used to check when the user is no longer scrolling.
    -   Add a scroll to top button on the page that’s only visible when the user scrolls below the fold of the page.
    -   Update/change the design/content.
    -   Make sections collapsible.

## Version Control

Although not a requirement, we recommend using Git from the very beginning. Make sure to commit often and to use well-formatted commit messages that conform to our  [Git Style Guide](https://udacity.github.io/git-styleguide/).

## Udacity Style Guides

You should write your code and markup to meet the specifications provided in these style guides:

-   [CSS Style Guide](http://udacity.github.io/frontend-nanodegree-styleguide/css.html)
-   [HTML Style Guide](http://udacity.github.io/frontend-nanodegree-styleguide/index.html)
-   [JavaScript Style Guide](http://udacity.github.io/frontend-nanodegree-styleguide/javascript.html)
-   [Git Style Guide](https://udacity.github.io/git-styleguide/)

## Still Not Sure How to Begin?

To reiterate, be sure that you are comfortable with the content from JavaScript and the DOM. After all, this entire project is about DOM manipulation!

A note on plagiarism: Viewing someone else’s code to get a general idea of implementation, then putting it away and starting to write your own code from scratch is okay.  **Please do not copy someone's code**, in whole or in part. For further details, check out this  [guide regarding plagiarism](https://udacity.zendesk.com/hc/en-us/categories/360000151251-Plagiarism).

# Project Submission: Landing Page

This project requires you to build a multi-section landing page, with a dynamically updating navigational menu based on the amount of content that is added to the page.

## Project Files

You can obtain the project code  [here](https://github.com/udacity/fend/tree/refresh-2019/projects/landing-page). To complete the project will mostly require modifying the  `js/app.js`  file, as well as modifications to the  `index.html`  and  `css/styles.css`  files to further update and customize your project.

## Rubric

Your project will be evaluated by a Udacity code reviewer according to the Landing Page  [project rubric](https://review.udacity.com/#!/rubrics/2658/view). Please make sure to re-review the rubric for detailed project requirements prior to submission.

## Submission

Once you've met all of the rubric requirements, you can submit your project as either a zip file or a Github repository link below.

# 项目概述

本次项目旨在为你提供操作 DOM 的真实场景，主要有两个目的：使你掌握向 DOM 动态添加数据的技能、向你展示 JavaScript 如何改善原本静态网站的可用性。此项目可能并不能触及所有技术细节，但是其中确实使用了一些非常常见的事件、方法和逻辑。

对于此项目，请在构建时尽可能进行一些重构和测试。你应该为添加的每项功能测试性能，可能这会花费与重构和测试代码一样多的时间。如果你花费 3 小时来理清逻辑，很可能也需要 3 小时来确认自己的代码是可能的最优解。随着技能水平的提升，这个过程会变得更加自然。注意，你需要确保最终提交的内容中，删除了这些调试代码。

## 我将构建什么？

你将构建一个多模块（Section）的落地页。通常，我们不知道通过 CMS 或 API 添加到页面的内容有多少。为了避免这个问题，我们可以将内容动态添加到页面中，通过导航菜单对此进行展示。此外，动态构建导航是了解虚拟 DOM 的重要前提（开始使用 JavaScript 框架时，你会体验到虚拟 DOM）。

为了改善用户体验，应该以某种方式区分正在浏览的模块。此外，当用户点击导航项目时，应该将页面滚动到对应的模块，而不是默认跳转。

这看起来似乎不太多，但是有很多相互依赖的活动，在开始开发之前，你需要计划要完成的逻辑。如果你觉得这个过程很快完成，那么可以添加一些附加功能，努力改善用户体验。

## 我将学到什么？

落地页项目将是你第一次将 HTML CSS 和 JavaScript 技能完全运用到一个大型项目。除了巩固这三项技术方面的技能，你还会发现将它们结合到一个复杂的应用中有多精彩。

以下是你在完成此项目过程中将遇到的一些示例问题：

-   理想的工作流程是什么？
-   我需要多少个文件？
-   先修改 HTML 还是 CSS？
-   我需要多少个 JavaScript 函数？
-   我的函数也应该这么多行代码吗？
-   可读性和性能哪个更重要？

每个问题都没有标准答案。可以在构建此项目时，与同期学员沟通，从项目审阅专家获得反馈，你将自然得出这些问题的答案。

# 项目说明

## 简介

本次项目需要你构建一个具有多模块的落地页，并且根据添加到页面的内容量，动态更新导航菜单。

## 项目审阅标准

优达学城的审阅专家会根据[项目审阅标准](https://review.udacity.com/#!/rubrics/2768/view)对你的项目进行审阅，请查看详细的项目要求。

## 获取初始代码

如果你想从头开始，不利用任何已有的文件，我们非常推荐！自己开发能学到最多的知识！但是从头开始的话，比较有挑战性，因此我们提供了项目起始代码（代码的“骨架”）供你使用。

你可以在[这里](https://github.com/udacity/fend/tree/refresh-2019)下载初始代码。

起始代码是项目的静态非交互版本，你可以对其进行完善开发。

## JavaScript 和 DOM

很棒！现在你已经有初始代码了。在继续之前，请确保自己已熟悉 JavaScript 和 DOM 课程中的内容。问自己几个问题：

-   [Document](https://developer.mozilla.org/zh-CN/docs/Web/API/Document)  是什么？
-   [事件](https://developer.mozilla.org/zh-CN/docs/Web/API/Event)是什么？
    -   如何[监听事件](https://developer.mozilla.org/zh-CN/docs/Web/API/EventTarget/addEventListener)？
    -   **事件委托**如何帮助我们避免太多事件？
    -   如果需要，请复习**浏览器事件**这节课的内容
-   如何使用以下两个方法访问元素？它们的区别是什么？
    -   [querySelector()](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/querySelector)
    -   [querySelectorAll()](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/querySelectorAll)
-   如何使用  [getElementbyId()](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/getElementById)  通过  `id`  选择 DOM 元素？
-   我们还可以使用  [getElementsByClassName()](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/getElementsByClassName)  访问元素，该方法返回什么？如何使用？
-   如何使用  [className](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/className)  属性？它返回什么？为什么有用？
-   [classList](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/classList#Methods)  有哪些不同的方法？
    -   提示：`add()`、`remove()`、`toggle()`  方法看起来尤其有用
-   每个元素都有  [innerHTML](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/innerHTML)  属性，展示了元素的内容标记。如何利用此属性来  **获取**  和  **设置**  内容？

# 开发策略

对于这个项目，你将在  **js/app.js**  中编写大部分代码。注意，在开始编写任何代码之前，对项目进行规划都非常重要。将项目分解为一些**小的**组件，并为每一组件制定策略，有了这些“好下手”的组件，就可以更容易地调试和解决出现的问题了。

你可以随意按照自己的设计工作流程实现功能，但是如果遇到困难，下方是一些步骤提示，可以帮助你开始项目：

1.  **先链接 app.js**。根据当前学到的知识，这个文件应该放在哪里？我们稍后会测试一些其他位置。
2.  **构建一个至少有三个模块（Section）的 HTML**。其他功能都基于这些模块。
    -   快速查看一下  **index.html**  中所有的 HTML 元素。注意它们的  `id`、`class`  和  `data`  属性。要操作 DOM，你要使用针对这些元素（以及你创建的元素）的工具和方法。
        -   有关 data 属性的复习，可以查看[这里](https://www.w3schools.com/tags/att_data-.asp).
    -   可以使用哪种数据结构存储这些模块？此数据结构可以表示页面的所有模块，所以建议将其保存到变量中。
    -   你要如何迭代（即循环遍历）此数据结构？
    -   思考一下，如何从该结构中创建一个 HTML  **无序列表**（即项目符号列表），将该列表放置在何处？
    -   思考一下，如何测试视口（viewport）中是否存在模块？
    -   执行哪些操作会导致与 DOM 的交互？
3.  **构建导航菜单**。根据页面的各个模块动态创建一个导航菜单。在你不确定内容管理系统（CMS）或 API 的项目数量时，这可能是一个特别有用的技巧。
    -   是否有监听构建导航的事件？
    -   在何处放置导航菜单？
    -   导航项中的文字从何处获取？导航项要锚定到何处？
    -   如何将每个导航项添加到菜单？（提示：有几种方法可以做到，搜索研究一下，确定哪种方式最适合自己的情况。性能如何？是否明晰？）
4.  **添加功能来区分视图中的模块**。浏览页面时，应将视口中/最靠近顶部的模块与其他模块区分开。
    -   是否有监听模块变成活跃状态的事件？
    -   如何测试应该突出显示哪个模块？
    -   如何使用  `classList`  [方法](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/classList#Methods)  来修改显示的 CSS？如何删除该 CSS？
    -   检查 HTML 和 CSS 文件，确保你选择的内容在其他位置也更新了。
5.  **添加功能来滚到到模块**。点击导航项应滚动到页面的相应模块。
    -   你监听的是什么事件？（提示：上面那句话中刚刚读到的）
    -   我们需要停止一个默认事件，如何停止？
    -   如果你不记得 HTML 页面锚元素的工作原理，请[查看文档的示例部分](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/a#Examples)，找出应该设置的变量。
    -   有几种用于滚动的 JavaScript 方法，哪个看起来最简单？
6.  **重构**。此时，你的代码应该可以正常工作。理想情况下，重构是在开发过程中进行的，但是作为一个新手开发者，你很可能没有全面了解如何正确地进行重构。我们来将项目清理一下。
    -   你是否使用了 linter 运行代码？我们要求你的代码完成后仍然遵循优达学城的标准，但是通过  [eslinter](https://eslint.org/demo)  运行代码，可以帮助你开始进行重构。
    -   是否使用了 ES6 的 const 和 let？
    -   是否所有函数都使用了 ES6 的箭头函数？
    -   你的代码是否遵循 DRY（Don't Repeat Yourself 不要重复自己）准则？有没有代码片段可以整合为帮助函数避免冗余？
    -   代码结构如何？你是否使用了合适作用域的变量，为主要功能创建了函数？如果你是 JavaScript 编程新手，可能会使用一个全局作用域的变量，后续了解有关闭包和设计模式的知识后，就能避免这种情况。但是将代码放入函数中是使代码更具可读性的一种好方法，也是避免全局作用域变量的一种好方法。
    -   是否使用了最恰当的迭代方法？
7.  **为 HTML 文档添加更多的模块**。查看导航的构建方式。
8.  **测试性能**。编写 JavaScript 的方式以及加载 JavaScript 的位置，都会影响性能。
    -   对比测试在头部加载脚本和在 body 末尾加载脚本，出现什么问题？有没有办法在不报错的情况下仍然在头部加载脚本？与在 body 末尾加载相比，性能如何？
9.  **建议：**
    -   当对应模块位于视口中时，为该导航项添加活动状态。
    -   不滚动时，隐藏固定的导航栏（页面加载时仍应存在）。
        -   提示：setTimeout 可用于检查用户何时不再滚动。
    -   添加一个【滚动到顶部】按钮，只有当用户滚动到页面的下方时，该按钮才可见。
    -   更新/更改设计/内容。
    -   使各个模块可折叠。

## 版本控制

虽然不是强制要求，但是我们建议你从一开始就使用 Git。确保经常 commit，并且使用格式清晰的 commit 消息（遵循优达学城的  [Git 样式指南](https://github.com/udacity/frontend-nanodegree-styleguide-zh/blob/master/%E5%89%8D%E7%AB%AF%E5%B7%A5%E7%A8%8B%E5%B8%88%E7%BA%B3%E7%B1%B3%E5%AD%A6%E4%BD%8D%E6%A0%B7%E5%BC%8F%E6%8C%87%E5%8D%97%20-%20Git.md)）。

## 优达学城前端样式指南

你的代码应遵循优达学城前端样式指南的规范：

-   [CSS 样式指南](https://github.com/udacity/frontend-nanodegree-styleguide-zh/blob/master/%E5%89%8D%E7%AB%AF%E5%B7%A5%E7%A8%8B%E5%B8%88%E7%BA%B3%E7%B1%B3%E5%AD%A6%E4%BD%8D%E6%A0%B7%E5%BC%8F%E6%8C%87%E5%8D%97%20-%20CSS.md)
-   [HTML 样式指南](https://github.com/udacity/frontend-nanodegree-styleguide-zh/blob/master/%E5%89%8D%E7%AB%AF%E5%B7%A5%E7%A8%8B%E5%B8%88%E7%BA%B3%E7%B1%B3%E5%AD%A6%E4%BD%8D%E6%A0%B7%E5%BC%8F%E6%8C%87%E5%8D%97%20-%20HTML.md)
-   [JavaScript 样式指南](https://github.com/udacity/frontend-nanodegree-styleguide-zh/blob/master/%E5%89%8D%E7%AB%AF%E5%B7%A5%E7%A8%8B%E5%B8%88%E7%BA%B3%E7%B1%B3%E5%AD%A6%E4%BD%8D%E6%A0%B7%E5%BC%8F%E6%8C%87%E5%8D%97%20-%20JavaScript.md)
-   [Git 样式指南](https://github.com/udacity/frontend-nanodegree-styleguide-zh/blob/master/%E5%89%8D%E7%AB%AF%E5%B7%A5%E7%A8%8B%E5%B8%88%E7%BA%B3%E7%B1%B3%E5%AD%A6%E4%BD%8D%E6%A0%B7%E5%BC%8F%E6%8C%87%E5%8D%97%20-%20Git.md)

## 仍然不确定如何开始？

重申一下，请确认自己掌握了 JavaScript 和 DOM 的知识。毕竟整个项目都是关于 DOM 操作的！

关于抄袭的说明：查看他人的代码了解实现想法，然后从头编写自己的代码是可以的。但是**请不要复制他人的代码**，不论是全部还是部分。更多信息可以参考[优达学城诚信准则](https://udacity.kf5.com/hc/kb/article/1223644/)。


# 项目提交：落地页（Landing Page）

本次项目需要你构建一个具有多个模块（Section）的落地页，并且根据添加到页面的内容量，动态更新导航菜单。

## 项目文件

可以在[此处](https://github.com/udacity/fend/tree/refresh-2019/projects/landing-page)获取项目代码。要完成此项目，通常需要修改  `js/app.js`、`index.html`  以及  `css/styles.css`  文件，来进一步更新和定制你的项目。

## 审阅标准

优达学城的审阅专家会根据[项目审阅标准](https://review.udacity.com/#!/rubrics/2768/view)对你的项目进行审阅，请在提交前确认已查看详细的项目要求。

## 项目提交

满足所有审阅要求后，你可以在下方提交打包后的 zip 文件或 Github 代码库链接。
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIzMzIyNDU5OF19
-->
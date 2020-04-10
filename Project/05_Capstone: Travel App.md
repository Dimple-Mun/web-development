# Project Summary

**旅行应用**

This project aims to give you the opportunity to put all of the skills you have learned into one project to build your own custom travel app. Due to the nature of this course, it is very JavaScript heavy, but it is still expected you create clean and appealing HTML/CSS. You will also be targeting the DOM, working with objects, and retrieving data from 3 APIs in which one of those is reliant on another to work. Finally, this is all going to be done in a Webpack environment, using an express server, and wrapped up with service workers.

For this project, refactor and test as much as possible while you are building. You should figure for every piece of functionality you add, you will likely spend just as much time testing and refactoring your code. If it takes you 5 hours to figure out the logic, it should likely take you another 5 hours determining that you wrote the best code possible. As your skills improve, this process will feel more natural. Make sure to remove any debugging code from your final submission.

The minimum requirements ask a fair amount from you, but the final app is quite simple. A roadmap to expand on the application and make it uniquely your own is provided.

## What You Will Build:

You will be building a travel application. It’s common to pull basic data from an API, but many applications don’t just pull the weather, they pull in multiple types of data, from different sources and occasionally one API will be required to get data from another API.

The project will include a simple form where you enter the location you are traveling to and the date you are leaving. If the trip is within a week, you will get the current weather forecast. If the trip is in the future, you will get a predicted forecast. The OpenWeather API is fantastic but it doesn’t let you get future data for free and it’s not that flexible with what information you enter; we are going to use the Dark Sky API for you to see how another API accomplishes the same goals. Dark Sky has one problem, it only takes in coordinates for weather data -- it’s that specific. So, we’ll need to get those coordinates from the Geonames API. Once we have all of this data, we’ll want to display an image of the location entered; for this, we will be using the Pixabay API.

This may not sound like a lot, but there is a fair amount of moving pieces that rely on each other to work. You’ll need to plan out the logic of what you are trying to accomplish before you begin developing. There are a lot of paths you can take, and what you choose to display and how you display it is somewhat flexible. It is highly recommended that after you meet the minimum requirements in the rubric, you continue debugging the UX and improve the project.

## What will I learn?

At this point, you have learned all of the technical skills necessary to complete this project. You will likely stumble along the way and find that there are some pieces you didn’t encounter in the past projects. Remember, if you get stuck, you should always look things up. Sometimes just articulating the problem renders a solution.

The following are just some of the questions that you’ll experience along the way:

-   What’s the ideal workflow?
-   How many files do I need?
-   How do I convert one project into another?
-   Should I redo the HTML/CSS first or go straight to the javascript?
-   How many JavaScript functions do I need?
-   Should my function be this many lines of code?
-   Is readability or performance more important?

There’s no single correct answer to each question. While building this project, working with peers, and getting feedback from the project reviewer -- you will naturally develop your own answers to these questions!

# Getting Started

## Introduction

This project requires you to build out a travel app that, at a minimum, obtains a desired trip location & date from the user, and displays weather and an image of the location using information obtained from external APIs. Given that this is the Capstone project, it's highly encouraged for you to go above and beyond, adding additional functionality and customization to truly stand out with a project you are proud to have at the top of your portfolio!

## Project Rubric

Your project will be evaluated by a Udacity code reviewer according to the Travel Planner App  [project rubric](https://review.udacity.com/#!/rubrics/2669/view). Please review for detailed project requirements.

## Get the Starter Code

If you'd like to start from scratch without any files, you are encouraged to do so! You learn the most by developing on your own! But, it can be a bit challenging having to start from scratch. There’s not the standard starter code you’re used to. If you would like to start with starter code, duplicate your code from project 3 and start there. Here is just one possibility for the visual of this project. Of course, you can style it how you choose, and extending the project will dictate the final appearance.

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/075c02bd-082b-4b09-bdc4-688630e7efe7/modules/eb6b8a12-4ba5-449b-9f27-be55cc41cee3/lessons/f04d6770-d0f2-4c4f-b5e2-199db5d3d53e/concepts/65c2663e-4eb8-46b9-8a3f-e88e928875df#)

![An example Travel App, both at minimum and with additional functionality](https://video.udacity-data.com/topher/2019/August/5d44825f_travel-app-project-mockup/travel-app-project-mockup.png)

An example Travel App, both at minimum and with additional functionality

## Before you begin...

Before moving forward, reacquaint yourself with project 3 & 4. After, ask yourself:

-   What is the  [Document](https://developer.mozilla.org/en-US/docs/Web/API/Document)?
-   What are  [events](https://developer.mozilla.org/en-US/docs/Web/API/Event)?
    -   How do we  [listen for them](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)?
-   How can we  [access elements](https://www.w3schools.com/js/js_htmldom_elements.asp)  within the DOM?
-   We can also access elements with  [getElementsByClassName()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName). What does this method return, and how do you use it?
-   Every element has an  [innerHTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML)  property that represents the markup of the element's content. How can you leverage this property to get and set content?
-   What is the  [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)  and how can we use it to get data?
-   What are  [callback functions](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)  and how do we use them appropriately?
-   What is  [asynchronous javascript](https://developers.google.com/web/fundamentals/primers/async-functions)?
-   How/Why do we use  [Express](https://expressjs.com/)?
-   How/Why do we use  [Webpack](https://webpack.js.org/)?
-   How/Why do we use  [service workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API)?

# Development Strategy

It's very important that you  _plan your project_  before you start writing any code! Break your project down into  _small_  pieces of work and strategize your approach to each one. With these bite-sized amounts, it'll be easier to debug and fix any issues that appear.

Feel free to implement your own design workflow, but if you get stuck -- here is a walkthrough to get you up and running!

1.  **Start by duplicating your project 3 weather app.**  Once duplicated, change the new project’s name to make certain you're not overwriting your old project. We are going to build off this project as a foundation.
2.  **Get webpack set up to work with this project.**  Use the skills you learned in project 4 to get your development environment going.
    -   Create your  `src`  folder first. The  `src`  folder should contain a client folder and a server folder.
    -   Your server folder should contain your  `server.js`  content.
    -   Your client folder should contain a  `js`  folder,  `media`  folder,  `styles`  folder, and  `views`  folder, as well as an  `index.js`  file.
    -   Your application js should go into the  `js`  file, your css into  `styles`, and your  `index.html`  into  `views`.
    -   Convert your stylesheet from a  `.css`  file to a  `.scss`  file
    -   Remember that webpack builds a  `dist`  file. You’ll need to update your server js to access the  `dist`  folder. (Hint:  `app.use(express.what goes here?)`)
    -   Your  `index.js`  file inside the client folder should import the main function of your application javascript, it should import your scss, and it should export your main function from your application javascript. But in order to import, where will you need to export it?
    -   In project 4, you may have added your event listeners to the buttons themselves. For this project, you should be using  `.addEventListener()`; If we are exporting functions from our  `application.js`  file, our event listeners can’t go there. Where can we put them? To call that exported function?
    -   Now that your src folder is set up, it’s time to get webpack going. You should already have a few dependencies installed from project 3. We need to add babel, babel loader, css loader, file loader, html loader, html webpack plugin, node sass, sass loader, style loader, webpack, webpack cli, and webpack dev server. Refer to your project 4 to see what’s there, most of these should have been in use there.
    -   Next, update the scripts in  `package.json`. You will want to have  `test`,  `dev`,  `start`, and  `build`.  **NOTE:**  Start will be for your express server, dev will be so that you can take advantage of web dev server. It is possible depending on your setup to run both of these with one command.
    -   Get your webpack config set up. Should be fairly similar to your language processing app webpack config. If you did not use webpack dev server in your language processing app, you will want to do so here. Additionally, using source maps will help you debug your css.
    -   To get webpack running, you’ll want to first run  `npm run dev`, then  `npm build`  to get your  `dist`  folder created. Once that is created you can run  `npm run dev`  and  `npm start`  simultaneously to have hot loading of your project as well as a working express environment.  **NOTE:**  If needed, reference the stripped-down version of project 3 with webpack in the starter documentation.
3.  **Create an account with  [Geonames](http://www.geonames.org/export/web-services.html).**
4.  **Replace the openweather api with geonames api.**  You already have one working api. What information needs to get adjusted so that instead of entering a zip code, you enter a city? We want to get the latitude, longitude, country, instead of getting the temperature, feeling, and date.
    -   The weather data array was named differently, what do we need to change the name to?
    -   The weather data only had 1 object in the array, the geoname api outputs multiple objects. How do we call the first object?
5.  **Introduce a countdown.**  You’ll need to add a text field to your project to get the date.
    -   What type of input should it be? What about cross browser rendering?
    -   We’re looking to see how soon the trip is, how can you get the information from the DOM and see how soon that date is?
    -   Where should you be storing that data once you have it?
6.  **Create an account with  [Dark Sky](https://darksky.net/dev).**
7.  **Integrate the Dark Sky api similarly to how you integrated the geoname api.**  What information needs to get adjusted for you to pull in the future weather? Getting a CORS error? Check out  [this article](https://medium.com/@dtkatz/3-ways-to-fix-the-cors-error-and-how-access-control-allow-origin-works-d97d55946d9)  for some options.  **NOTE:**  If you see that your app is working, but it takes several clicks to get all of the data, think of why this could be. This is possibly the most challenging part of the project. There is a major hint located in the  _Before you Begin_  section. If you’re unable to figure it out, and your app still works with a few clicks, continue working on it, it may come to you later, or you’ll get guidance from your reviewer when you submit the app.
    -   How does the Dark Sky API distinguish from current forecast and future forecasts? Does the API change in any way?
    -   How will we include the date? What format does it need to be in? How can we change it to the appropriate format?
8.  **Create an account with  [Pixabay](https://pixabay.com/api/docs/).**
9.  **Integrate the Pixabay API similarly to how you integrated the Geoname/Dark Sky APIs.**  What information are you going to submit to the API to achieve an appropriate image? What if there are no results?
    -   What Parameters will you want to set to pull in images?
    -   How will you submit your data from the location field to a Pixabay URL parameter without having spaces in the url?
10.  **Choose one of the items from the suggested list to add in.**  The items vary in complexity, but you must choose at least 1, all others are optional.
11.  **REFACTOR.**  At this point, your code should be working properly. Ideally, refactoring happens while you are developing, but as a new developer, you often don’t have the whole picture in your head to be able to do so properly. Let’s clean the project up.
    -   Have you run your code through a linter? We request you still follow Udacity standards when the code is complete, but running it through an  [eslinter](https://eslint.org/demo)  is going to help you get started in refactoring.
    -   Are you using ES6 const and let?
    -   Are all your functions using ES6 arrow functions?
    -   Is your code DRY? Are there any pieces that would be better served as a helper function to avoid duplication?
    -   How is your code structured? Have you created functions for the main functionality with properly scoped variables? Starting out it’s likely that you will have a globally scoped variables on occasion until you learn more about closures and design patterns. But placing your code into functions is a great way to make your code more readable and a way to avoid globally scoped variables.
    -   Are your project files named in a way that makes sense?
12.  **Add in services workers.**  Refer to project 4 for guidance.

## Extend your Project Further - Roadmap/Strategy

You'l need to implement  _at least one_  of the below in the project. If you’re going to do any of the suggested tasks, it’s recommended that you hold off on service workers until you are closer to submitting. This is a good use for comments.

-   Add end date and display length of trip.
-   Pull in an image for the country from Pixabay API when the entered location brings up no results (good for obscure localities).
-   Allow user to add multiple destinations on the same trip.
    -   Pull in weather for additional locations.
-   Allow the user to add hotel and/or flight data.
    -   Multiple places to stay? Multiple flights?
-   Integrate the  [REST Countries API](https://restcountries.eu/)  to pull in data for the country being visited.
-   Allow the user to remove the trip.
-   Use  [Local Storage](https://www.taniarascia.com/how-to-use-local-storage-with-javascript/)  to save the data so that when they close, then revisit the page, their information is still there.
-   Instead of just pulling a single day forecast, pull the forecast for multiple days.
-   Incorporate icons into forecast.
-   Allow user to Print their trip and/or export to PDF.
-   Allow the user to add a todo list and/or packing list for their trip.
-   Allow the user to add additional trips (this may take some heavy reworking, but is worth the challenge).
    -   Automatically sort additional trips by countdown.
    -   Move expired trips to bottom/have their style change so it’s clear it’s expired.

## Version Control

Although not a requirement, we recommend using Git from the very beginning. Make sure to commit often and to use well-formatted commit messages that conform to our  [Git Style Guide](https://udacity.github.io/git-styleguide/).

## Udacity Style Guides

You should write your code and markup to meet the specifications provided in these style guides:

-   [CSS Style Guide](http://udacity.github.io/frontend-nanodegree-styleguide/css.html)
-   [HTML Style Guide](http://udacity.github.io/frontend-nanodegree-styleguide/index.html)
-   [JavaScript Style Guide](http://udacity.github.io/frontend-nanodegree-styleguide/javascript.html)
-   [Git Style Guide](https://udacity.github.io/git-styleguide/)

## Still Not Sure How to Begin?

To reiterate, be sure that you are comfortable with the content from all previous coursework, especially your weather and language processing apps; you should keep those handy to reference through the project.

A note on plagiarism: Viewing someone else’s code to get a general idea of implementation, then putting it away and starting to write your own code from scratch is okay.  **Please do not copy someone's code**, in whole or in part. For further details, check out this  [guide regarding plagiarism](https://udacity.zendesk.com/hc/en-us/categories/360000151251-Plagiarism).


# Project Submission: FEND Capstone Project: Travel App

This project requires you to build out a travel app that, at a minimum, obtains a desired trip location & date from the user, and displays weather and an image of the location using information obtained from external APIs. Given that this is the Capstone project, it's highly encouraged for you to go above and beyond, adding additional functionality and customization to truly stand out with a project you are proud to have at the top of your portfolio!

## Project Files

If you'd like to start from scratch without any files, you are encouraged to do so! You learn the most by developing on your own! But, it can be a bit challenging having to start from scratch. There’s not the standard starter code you’re used to. If you would like to start with starter code, duplicate your code from project 3 and start there. See the earlier  **Getting Started**  page for an example visual of one potential finished product.

## Rubric

Your project will be evaluated by a Udacity code reviewer according to the Travel Planner App  [project rubric](https://review.udacity.com/#!/rubrics/2669/view). Please review for detailed project requirements.

## Submission

Once you've met all of the rubric requirements, you can submit your project as either a zip file or a Github repository link below.

# 项目概述

本次项目旨在提供机会，将你学到的所有前端技能整合到一个项目中，构建自己的旅行应用。由于本课程的性质，项目会非常侧重 JavaScript，但是同样也希望你能创建干净且吸引人的 HTML/CSS。你还需要定位 DOM、使用对象，以及从 3 个 API（其中之一还要依赖于另一个 API 来工作）中获取数据。最后，所有这一切都要在 webpack 环境中完成，使用 Express 服务器和 Service Worker。

对于此项目，请在构建时尽可能进行一些重构和测试。你应该为添加的每项功能测试性能，可能这会花费与重构和测试代码一样多的时间。如果你花 5 小时来理清逻辑，很可能也需要 5 小时来确认自己的代码是可能的最优解。随着技能水平的提升，这个过程会变得更加自然。注意，你需要确保最终提交的内容中，删除了这些调试代码。

这似乎涉及到很多方面的知识，但最终的应用程序最低要求非常简单。你还可以提供旅行路线图对应用进行扩展，自定义设计，使其成为属于自己的独特作品。

## 我将构建什么？

你将构建一个旅行应用程序。从一个 API 提取基本数据很常见，但是很多应用程序不仅只提取天气数据，还要从不同来源提取多种类型的数据，有时要从某个 API 提取数据，可能还需要依赖另一个 API。

本项目包括一个简单的表单，可以在其中输入要旅行的地点和出发日期。如果旅行在一周内，你会获得当前的天气预报。如果旅行是在一周后，你会获得预测的天气预报。OpenWeather API 很出色，但是不能免费获得未来的数据，而且输入信息也不够灵活。本次项目要使用的是 Dark Sky API，这可以帮助你了解另一个 API 如何实现相同的功能。Dark Sky 有一个问题，只能通过坐标来获取天气数据。因此，我们需要从 Geonames API 获取旅行地点的坐标。获得这些数据后，还要使用 Pixabay API 获取输入位置的图像并显示在应用中。

这看起来不太多，但是很多其实都是相互依赖的，在开发之前，思考下自己需要完成哪些逻辑。完成项目有很多方式，选择显示的内容以及显示方式也都比较灵活。强烈建议你在满足审阅标准的最低要求之后，继续调试用户体验，优化项目。

## 我将学到什么？

到目前为止，你已经学习了完成此项目所需的所有技能。你可能会遇到一些困难，发现有些内容在之前的项目中没有遇到过。记住，遇到困难时应该去搜索引擎搜索或者查找官方文档。很多时候只要能明确描述问题，就能在搜索引擎找到解决方案。

以下是你在完成此项目过程中，可能会遇到的一些示例问题：

-   理想的工作流程是什么？
-   需要多少个文件？
-   如何将一个项目转变为另一个项目？
-   应该先重做 HTML/CSS，还是直接开始处理 JavaScript？
-   需要多少个 JavaScript 函数？
-   我的函数也应该这么多行代码吗？
-   可读性和性能哪个更重要？

每个问题都没有标准答案。可以在构建此项目时，与同期学员沟通，从项目审阅专家获得反馈，慢慢就能得出这些问题的答案了。

# 项目说明

## 简介

本次项目需要构建一个旅行应用程序，该应用最少应该具有这样的功能：从用户那里获取旅行地点和日期，使用从外部 API 获取的信息来显示旅行地点的天气和图像。鉴于这是毕业项目，因此强烈建议你超越常规，添加其他功能和自定义设置，使其在你的简历作品集中脱颖而出！

## 项目审阅标准

优达学城的审阅专家会根据旅行应用[项目要求](https://review.udacity.com/#!/rubrics/2779/view)对你的项目进行审阅，请查看详细的项目要求。

## 获取初始代码

如果你想从头开始，不利用任何已有的文件，我们非常推荐！自己开发能学到最多的知识！但是从头开始的话，比较有挑战性。本次项目没有提供专门的起始代码，如果你想要从起始代码开始开发，可以复制项目 3 的起始代码。以下只是此项目界面的一种可能，当然，你也可以选择其他样式，另外，项目的扩展功能也会改变界面的最终表现。

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/dd8d5fb1-34e5-4174-8373-2bc8f28f3c4f/modules/eb6b8a12-4ba5-449b-9f27-be55cc41cee3/lessons/f04d6770-d0f2-4c4f-b5e2-199db5d3d53e/concepts/65c2663e-4eb8-46b9-8a3f-e88e928875df#)

![旅行应用示例，包括最低要求和额外功能](https://video.udacity-data.com/topher/2019/August/5d44825f_travel-app-project-mockup/travel-app-project-mockup.png)

旅行应用示例，包括最低要求和额外功能

## 开始之前

在继续之前，请复习项目 3 和项目 4，根据以下问题查缺补漏：

-   [Document](https://developer.mozilla.org/zh-CN/docs/Web/API/Document)  是什么？
-   [事件](https://developer.mozilla.org/zh-CN/docs/Web/API/Event)是什么？
    -   如何[监听事件](https://developer.mozilla.org/zh-CN/docs/Web/API/EventTarget/addEventListener)？
-   在 DOM 中如何[访问元素](https://www.w3schools.com/js/js_htmldom_elements.asp)？
-   我们还可以使用  [getElementsByClassName()](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/getElementsByClassName)  访问元素，该方法返回什么？如何使用？
-   每个元素都有  [innerHTML](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/innerHTML)  属性，展示了元素的内容标记。如何利用此属性来  **获取**  和  **设置**  内容？
-   [Fetch API](https://developer.mozilla.org/zh-CN/docs/Web/API/Fetch_API)  是什么？如何利用其获得数据？
-   [回调函数](https://developer.mozilla.org/zh-CN/docs/Glossary/Callback_function)是什么？如何恰当使用？
-   [异步 JavaScript](https://developers.google.com/web/fundamentals/primers/async-functions)是什么？
-   为什么要使用  [Express](https://expressjs.com/)  以及如何使用？
-   为什么要使用  [Webpack](https://webpack.js.org/)  以及如何使用？
-   为什么要使用  [Service Worker](https://developer.mozilla.org/zh-CN/docs/Web/API/Service_Worker_API)  以及如何使用？

# 开发策略

在开始编写任何代码之前，对项目进行规划都非常重要。将项目分解为一些**小的**组件，并为每一组件制定策略，有了这些“好下手”的组件，就可以更容易地调试和解决出现的问题了。

你可以随意按照自己的设计工作流程实现功能，但是如果遇到困难，下面是一些步骤提示，可以帮助你开始项目：

1.  **复制项目 3 天气应用作为起始代码。**复制之后，修改项目名称，避免覆盖旧项目，我们将以这个项目为基础，进行开发。
2.  **针对此项目设置 webpack。**使用项目 4 学习的技能设置开发环境。
    -   首先，创建  `src`  文件夹。`src`  文件夹中应该包含 client 和 server 文件夹。
    -   server 文件夹中应包含  `server.js`  内容。
    -   client 文件夹中应包含  `js`、`media`、`styles`、`views`  文件夹以及一个  `index.js`  文件
    -   应用的 js 代码应该位于  `js`  文件中，css 代码位于  `styles`  文件夹，`index.html`  位于  `views`  文件夹。
    -   将样式表从  `.css`  文件转换为  `.scss`  文件。
    -   注意，webpack 会生成一个  `dist`  文件夹。需要更新服务器 js 使其引用  `dist`  文件夹。（提示：`app.use(express.这里需要修改为什么？)`）
    -   client 文件夹中的  `index.js`  文件应该导入（import）应用 JavaScript 的主函数，导入 scss，你的应用 JavaScript 中应该导出（export）其主函数。要完成导入，需要先在哪里将其导出？
    -   在项目 4 中，你可能将事件监听器添加到了按钮身上。对于这个项目，你应该要使用  `.addEventListener()`，如果我们要从  `application.js`  文件中导出函数，那么事件监听器没办法触及。要调用导出的函数，可以将事件监听器放到哪里呢？
    -   src 文件夹设置好之后，开始使用 webpack。你应该已经在项目 3 安装了一些依赖项，我们需要添加 babel、babel-loader、css-loader、file-loader、html-loader、html-webpack-plugin、node-sass、sass-loader、style-loader、webpack、webpack-cli 以及 webpack-dev-server。参考项目 4，应该已经使用过大部分。
    -   接下来，更新  `package.json`  中的脚本，需要有  `test`、`dev`、`start`  和  `build`。  **注意：**start 是针对 Express 服务器，dev 使你可以使用 Web 开发服务器，根据你的设置，可以使用一个命令运行这两个脚本。
    -   设置 webpack 配置，这应该与语言处理应用程序 webpack 配置非常相似。如果你未在语言处理应用程序中使用 webpack 开发服务器，则需要在此处使用。此外，使用源映射能帮助你调试 css。
    -   要运行 webpack，首先需要运行  `npm run dev`，然后运行  `npm build`  来创建  `dist`  文件夹。创建完成后，你可以同时运行  `npm run dev`  和  `npm start`  来热加载项目以及可以正常运行的 Express 环境。
3.  **创建一个  [Geonames](http://www.geonames.org/export/web-services.html)  账号。**
4.  **用 Geonames API 替换 OpenWeather API。**你已经有一个可以使用的 API。需要调整哪些信息，使其可以输入城市而不是输入邮政编码？我们要获取纬度、经度、国家信息，而不是获取温度、感受和日期。
    -   天气数据数组的名称不同，需要将名称修改为什么？
    -   天气数据在数组中只有 1 个对象，Geonames API 输出多个对象。如何调用第一个对象？
5.  **引入倒计时。**你需要在项目中添加一个文本字段来获取日期。
    -   应该是什么类型的输入？跨浏览器渲染怎么办？
    -   我们想要了解还有多久开始旅行，那么如何从 DOM 中获得信息以及如何判断该日期还有多久呢？
    -   拥有数据后，将其存储在何处？
6.  **创建一个  [Dark Sky](https://darksky.net/dev)  账号。**
7.  **集成 Dark Sky API 的方式与集成 geoname API 的方式类似。**要获取未来的天气，需要调整哪些信息？收到 CORS 错误？请查看[这篇文章](https://medium.com/@dtkatz/3-ways-to-fix-the-cors-error-and-how-access-control-allow-origin-works-d97d55946d9)了解如何处理。  **注意：**如果你看到自己的应用可以运行，但是需要点击几次才能获取所有数据，思考一下为何如此。这可能是项目中最具挑战性的部分。在**开始之前**部分中，有一个主要提示。如果你没办法处理，应用中仍然需要点击几次才可以正常运行，也可以在提交项目时，从审阅专家处获得指导。
    -   Dark Sky API 如何区分当前的天气预报和未来的天气预报？API 是否有一些对应的改动？
    -   如何包含日期？日期应该是什么格式？如何将其修改为适当的格式？
8.  **创建一个  [Pixabay](https://pixabay.com/api/docs/)  账号。**
9.  **像集成 Geoname/Dark Sky API 一样，集成 Pixabay API。**要向 API 提交哪些信息来获取适当的图像？如果没有结果怎么办？
    -   要设置哪些参数来获取图像？
    -   如何将 location 字段的数据提交到 Pixabay URL 参数，且 url 中不包含空格？
10.  **从建议列表中选择一项进行添加。**建议列表中的各项复杂度差异较大，但你必须至少选择一项，其他项可选。
11.  **重构。**此时，你的代码应该可以正常工作。理想情况下，重构是在开发过程中进行的，但是作为一个新手开发者，你很可能没有全面了解如何正确地进行重构。我们来将项目清理一下。
    -   你是否使用了 linter 运行代码？我们要求你的代码完成后仍然遵循优达学城的标准，但是通过  [eslinter](https://eslint.org/demo)  运行代码，可以帮助你开始进行重构。
    -   是否使用了 ES6 的 const 和 let？
    -   是否所有函数都使用了 ES6 的箭头函数？
    -   你的代码是否遵循 DRY（Don't Repeat Yourself 不要重复自己）准则？有没有代码片段可以整合为帮助函数避免冗余？
    -   代码结构如何？你是否使用了合适作用域的变量，为主要功能创建了函数？如果你是 JavaScript 编程新手，可能会使用一个全局作用域的变量，后续了解有关闭包和设计模式的知识后，就能避免这种情况。但是将代码放入函数中是使代码更具可读性的一种好方法，也是避免全局作用域变量的一种好方法。
    -   项目文件是否使用了有意义的名称？
12.  **添加 Service Worker。**参照项目 4 的指导说明。

## 进一步扩展项目 - 路线图/策略

以下选项中，你需要在项目中实现**至少一项**。如果你准备添加以下功能，建议推迟添加 Service Worker，直到接近提交为止，可以先将相关代码注释掉。

-   添加结束日期，显示行程长度。
-   从 Pixabay API 中提取图像，当输入的位置没有显示任何结果时（比如一些不常见的旅行目的地），提取一张该国家的图像。
-   允许用户在同一行程中添加多个目的地。
    -   为添加的位置获取天气。
-   允许用户添加酒店和航班数据。
    -   可以住多个酒店？多个航班？
-   集成  [REST Countries API](https://restcountries.eu/)  获取准备访问的国家数据。
-   允许用户删除行程。
-   使用[本地存储（local storage）](https://www.taniarascia.com/how-to-use-local-storage-with-javascript/)来保存数据，以便关闭后重新访问时，这些信息仍然存在。
-   提取多天的天气预报，而不是仅提取一天的天气。
-   在天气预报中纳入图标。
-   允许用户打印行程或导出为 PDF。
-   允许用户为其行程添加待办事项列表。
-   允许用户添加其他行程（这可能需要重做之前的很多内容，但值得挑战）。
    -   通过倒计时自动对其他行程进行分类。
    -   将过期的行程放到最下方，并且对其样式进行更改，使其可以明显表现为已过期。

## 版本控制

虽然不是强制要求，但是我们建议你从一开始就使用 git。建议经常 commit，并且使用格式清晰的 commit 消息（遵循优达学城的  [git 样式指南](https://github.com/udacity/frontend-nanodegree-styleguide-zh/blob/master/%E5%89%8D%E7%AB%AF%E5%B7%A5%E7%A8%8B%E5%B8%88%E7%BA%B3%E7%B1%B3%E5%AD%A6%E4%BD%8D%E6%A0%B7%E5%BC%8F%E6%8C%87%E5%8D%97%20-%20Git.md)）。

## 优达学城前端样式指南

你的代码应遵循优达学城前端样式指南的规范：

-   [CSS 样式指南](https://github.com/udacity/frontend-nanodegree-styleguide-zh/blob/master/%E5%89%8D%E7%AB%AF%E5%B7%A5%E7%A8%8B%E5%B8%88%E7%BA%B3%E7%B1%B3%E5%AD%A6%E4%BD%8D%E6%A0%B7%E5%BC%8F%E6%8C%87%E5%8D%97%20-%20CSS.md)
-   [HTML 样式指南](https://github.com/udacity/frontend-nanodegree-styleguide-zh/blob/master/%E5%89%8D%E7%AB%AF%E5%B7%A5%E7%A8%8B%E5%B8%88%E7%BA%B3%E7%B1%B3%E5%AD%A6%E4%BD%8D%E6%A0%B7%E5%BC%8F%E6%8C%87%E5%8D%97%20-%20HTML.md)
-   [JavaScript 样式指南](https://github.com/udacity/frontend-nanodegree-styleguide-zh/blob/master/%E5%89%8D%E7%AB%AF%E5%B7%A5%E7%A8%8B%E5%B8%88%E7%BA%B3%E7%B1%B3%E5%AD%A6%E4%BD%8D%E6%A0%B7%E5%BC%8F%E6%8C%87%E5%8D%97%20-%20JavaScript.md)
-   [Git 样式指南](https://github.com/udacity/frontend-nanodegree-styleguide-zh/blob/master/%E5%89%8D%E7%AB%AF%E5%B7%A5%E7%A8%8B%E5%B8%88%E7%BA%B3%E7%B1%B3%E5%AD%A6%E4%BD%8D%E6%A0%B7%E5%BC%8F%E6%8C%87%E5%8D%97%20-%20Git.md)

## 仍然不确定如何开始？

重申一下，请确认自己对前面的所有课程内容熟练掌握，尤其是天气和语言处理应用程序，在本项目中你应该可以灵活参考这些内容。

关于抄袭的说明：查看他人的代码了解实现想法，然后从头编写自己的代码是可以的。但是**请不要复制他人的代码**，不论是全部还是部分。更多信息可以参考[优达学城诚信准则](https://udacity.kf5.com/hc/kb/article/1223644/)。


# 项目提交：前端工程师毕业项目 - 旅行应用

本次项目需要你构建一个旅行应用程序，该应用最少应该具有这样的功能：从用户那里获取旅行地点和日期，使用从外部 API 获取的信息来显示旅行地点的天气和图像。鉴于这是毕业项目，因此强烈建议你超越常规，添加其他功能和自定义设置，使其在你的简历作品集中脱颖而出！

## 项目文件

如果你想从头开始，不利用任何已有的文件，我们非常推荐！自己开发能学到最多的知识！但是从头开始的话，比较有挑战性。本次项目没有提供专门的起始代码，如果你想要从起始代码开始开发，可以复制项目 3 的起始代码。另外，查看前面的**项目说明**页面，可以看到一个潜在成品的界面示例。

## 审阅标准

优达学城的审阅专家会根据旅行应用[项目要求](https://review.udacity.com/#!/rubrics/2779/view)对你的项目进行审阅，请在提交前确认已查看详细的项目要求。

## 项目提交

满足所有审阅要求后，你可以在下方提交打包后的 zip 文件或 GitHub 代码库链接。
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTk0MDIyODYwXX0=
-->
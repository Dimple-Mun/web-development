> Web API's and Asynchronous Applications
# Getting Started

## Introduction

**气象杂志应用**

This project requires you to create an asynchronous web app that uses Web API and user data to dynamically update the UI for a Weather-Journal App.

## Project Rubric

Your project will be evaluated by a Udacity code reviewer according to the Weather-Journal  [project rubric](https://review.udacity.com/#!/rubrics/2655/view). Please review the rubric for detailed project requirements. If you'd like to start from scratch without any files, you are encouraged to do so! You learn the most by developing on your own. But, it can be a bit challenging having to start from scratch, so we do provide a starter project (i.e., a "skeleton") to use.

## Get the Starter Code

You can download the starter code below by cloning the specific branch 'refresh-2019':

-   [The Weather Journal project repository](https://github.com/udacity/fend/tree/refresh-2019)

The starter code has all the elements and CSS you will need to complete the project, plus a little help getting started with the JavaScript. If you decide to start development on your own and then get stuck, you can always take a peek at the starter code available at the links provided for inspiration.

If you want to try the project without the starter code, and would like to use a comments only version of the finished JS code, you can find that at the link below.

-   [Comments only version of final JS code](https://github.com/udacity/fend/tree/refresh-2019/projects/weather-journal-app/commentsOnlyJS)  (`commentsOnlyJS`  directory)

# Web APIs and Asynchronous Applications

Great! You now have the starter code. Before moving forward, make sure you are comfortable with the content from Web APIs and Asynchronous Applications.

Ask yourself:

-   How do I setup a  [Node environment with Express](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/Introduction)  and the necessary project dependencies?
-   How do I setup  [a server with GET and POST routes](https://expressjs.com/en/guide/routing.html)?
-   How do I create developer credentials for a Web API?
-   How do I use the  [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)  with my credentials and user input to get dynamic data into my app routes?
-   How do I access a GET route on the server side, from a function called on the client side?
-   How do I  [chain Promises](https://javascript.info/promise-chaining)  together
-   How do I access HTML elements with JavaScript and set their properties dynamically?

# Development Strategy

For this project, you will be writing most of your code in two files:  `server.js`  and  `website/app.js`. Note that it's very important that you plan your project before you start writing any code! Break your project down into small pieces of work and strategize your approach to each one. With these bite-sized amounts, it'll be easier to debug and fix any issues that appear.

## Testing

Testing your code as you go is an excellent development approach. If you would like to write and run tests for parts of your implementation code, you can use the file  `tests.js`  to see examples of test code you might write along the development path.

Feel free to implement your own design workflow, but if you get stuck -- here is a walkthrough to get you up and running!

1.  _Start by setting up your project environment._  Make sure Node is installed from the terminal. Install the packages Express, Body-Parser, and Cors from the terminal and them include them your  `server.js`  file.
    -   Create a server running on the port of your choosing
    -   Add a  `console.log()`  to the server callback function, and test that your server is running using Node in the terminal to run the file  `server.js`
2.  _Add a GET route that returns the  `projectData`  object in your server code_  Then, add a POST route that adds incoming data to  `projectData`.
    -   The POST route should anticipate receiving three pieces of data from the request body
        -   temperature
        -   date
        -   user response
    -   Make sure your POST route is setup to add each of these values with a key to  `projectData`.
3.  _Acquire API credentials from OpenWeatherMap website_. Use your credentials and the base url to create global variables at the top of your  `app.js`  code.
    -   Write an  `async`  function in  `app.js`  that uses  `fetch()`  to make a GET request to the OpenWeatherMap API.
    -   Create an event listener for the element with the id:  `generate`, with a callback function to execute when it is clicked.
    -   Inside that callback function call your  `async`  GET request with the parameters:
        -   base url
        -   user entered zip code (see input in html with id  `zip`)
        -   personal API key
4.  After your successful retrieval of the weather data, you will need to chain another Promise that makes a POST request to add the API data, as well as data entered by the user, to your app.
    
    -   You will need to write another  `async`  function to make this POST request.
    -   The function should receive a path and a data object.
    -   The data object should include
        -   temperature
        -   date
        -   user response
    -   Remember, you can access the value of DOM elements by selecting them in your JS code.
5.  _Finally, chain another Promise that updates the UI dynamically_  Write another  `async`  function that is called after the completed POST request. This function should retrieve data from our app, select the necessary elements on the DOM (`index.html`), and then update their necessary values to reflect the dynamic values for:
    
    -   Temperature
    -   Date
    -   User input

# Project Submission: Weather Journal App with Asynchronous JavaScript

This project requires you to create an asynchronous web app that uses Web API and user data to dynamically update the UI in a Weather Journal application.

## Project Files

You can obtain the project code  [here](https://github.com/udacity/fend/tree/refresh-2019/projects/weather-journal-app). To complete the project will require modifying the  `server.js`  file and the  `website/app.js`  file. You can see  `index.html`  for element references, and once you are finished with the project steps, you can use  `style.css`  to style your application to customized perfection.

## Rubric

Your project will be evaluated by a Udacity code reviewer according to the Weather-Journal  [project rubric](https://review.udacity.com/#!/rubrics/2655/view). Please make sure to re-review the rubric for detailed project requirements prior to submission.

## Submission

Once you've met all of the rubric requirements, you can submit your project as either a zip file or a Github repository link below.

# 准备开始

## 介绍

该项目旨在使用 Web API 和用户数据构建异步 Web 应用：气象杂志，实现动态刷新界面功能。

## 审阅标准

审阅专家会根据[审阅标准](https://review.udacity.com/#!/rubrics/2780/view)审阅你的代码，提交项目前，请仔细阅读审阅标准，了解详细的项目要求。 在实战中学习是最好的学习方式，但是从头开始可能会略显困难，因此我们提供了初始代码帮助你上手。如果你要自己从头开始，当然我们也是鼓励的，加油！

## 获取初始代码

你可以克隆下面的 repo，切换到 'refresh-2019' 分支获取初始代码：

-   [气象杂志 repo](https://github.com/udacity/fend/tree/refresh-2019)

初始代码已经包含项目所需的所有 HTML 和 CSS 文件，你只需要修改 JavaScript 文件就可以完成项目。如果你决定从头开始，但是不小心卡住了，那么从初始代码中获取灵感不失为一个好的选择。

如果你想从头开始，我们还提供了一个只包含注释的版本，按照注释给出的线索，一步一步去做就可以了：

-   [注释版本](https://github.com/udacity/fend/tree/refresh-2019/projects/weather-journal-app/commentsOnlyJS)

# Web API 和异步应用

恭喜，你现在已经有了初始代码。在进入下一步之前，确保你已经掌握了 Web API 和异步应用的知识。

尝试问自己下面几个问题：

-   如何[使用 Express 配置 Node 开发环境](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/Introduction)？如何引入项目依赖？
-   如何[搭建一个具备 GET 和 POST 路由功能的服务器](https://expressjs.com/en/guide/routing.html)？
-   如何申请访问 Web API 的用户凭证？
-   如何使用  [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)  获取数据？
-   如何在服务器端处理 GET 请求？如何在客户端发起 GET 请求？
-   如何[链接 Promises](https://javascript.info/promise-chaining)？
-   如果使用 JavaScript 访问 HTML 元素并动态修改其属性？

# 开发策略

你需要修改  `server.js`  和  `website/app.js`  完成本项目。凡事预则立，不预则废。在写代码前，一个详细的规划是很有必要的。将项目拆分，分而治之，这样在完成每一部分时会更容易调试。

## 测试

边写边测是一种很好的开发方式。请参考  `tests.js`  中的示例学习如何添加测试。

你可以自己决定如何完成该项目，万一卡壳也没关系，我们给出了下面五条锦囊妙计帮你过关：

1.  _先配置好开发环境_，Node 装好后，依次在终端安装 Express、Body-Parser 和 Cors，并在  `server.js`  中引入。
    -   创建服务器并在选定端口运行。
    -   在回调函数中添加  `console.log()`  帮助调试，在终端使用 Node 运行  `server.js`  启动服务器。
2.  _在服务器端添加 GET 路由，返回  `projectData`  对象_。然后添加 POST 路由，将客户端请求中的数据存入  `projectData`。
    -   传给 POST 路由的请求体中包含三类信息：
        -   温度
        -   日期
        -   用户输入
    -   确保在 POST 路由中将这些信息都存入  `projectData`。
3.  _从 OpenWeatherMap 官网获得用于访问 Web API 的用户凭证_。在  `app.js`  最前面声明全局变量，保存用户凭证和基准 URL。
    -   在  `app.js`  中编写异步函数，使用  `fetch()`  发送 GET 请求，从 OpenWeatherMap API 取回数据。
    -   为 DOM 元素  `generate`  注册事件监听器，当点击时执行回调函数。
    -   在回调函数内调用异步函数获取数据，该函数需要三个参数：
        -   基准 URL
        -   用户输入的邮政编码（可以在 DOM 中查找 id 为  `zip`  的元素）
        -   API 私钥
4.  成功拿到气象数据后，以链接方式使用另一个 Promise 发起 POST 请求，将从 API 中拿到的数据和用户输入的数据存入你的 Web 应用。
    
    -   你需要再编写一个异步函数发起 POST 请求。
    -   该函数需要两个参数：路径和数据。
    -   数据需包含：
        -   温度
        -   日期
        -   用户反馈
    -   你可以在 JavaScript 代码中拿到具体 DOM 元素的属性。
5.  _最后，再使用一个 Promise 动态更新用户界面_。再编写一个异步函数，当 POST 请求成功返回后，从应用和 DOM 元素中获取数据，动态更新用户界面：
    
    -   温度
    -   日期
    -   用户输入


# 项目提交：使用异步 JavaScript 构建气象杂志应用

该项目旨在使用 Web API 和用户数据构建异步 Web 应用：气象杂志，实现动态刷新界面功能。

## 项目文件

学员可从  [Github](https://github.com/udacity/fend/tree/refresh-2019/projects/weather-journal-app)  下载初始代码，项目要求修改  `server.js`  和  `website/app.js`  实现主体功能。请查看  `index.html`  定位 DOM 元素，功能完成后，学员还可修改  `style.css`  美化页面。

## 审阅标准

审阅专家会根据[审阅标准](https://review.udacity.com/#!/rubrics/2780/view)审阅你的代码，提交项目前，请仔细阅读审阅标准，了解详细的项目要求。

## 提交项目

当你觉得项目满足要求时，请把整个项目打包，以 zip 文件的形式上传，或者输入项目在 Github 上的 URL 提交。
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzMxMTczMjEzXX0=
-->
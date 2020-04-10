# *Lesson 1 课程介绍*
## 课程大纲

-   **第一课**: 简介
-   **第二课**: 搭建 Node 和 Express 开发环境
-   **第三课**: HTTP 请求和路由
-   **第四课**: 异步 JavaScript

学完该课，你将具备以下能力：

-   在本机搭建  _Node_  和  _Express_  环境，开发 Web 应用。
-   搭建服务器，通过 Web 应用路由数据。
-   在 Web 应用中集成外部 API。
-   在 Web 应用中使用 HTTP  `GET`  和  `POST`  请求存取数据。
-   使用 HTML 表单，和由第三方 API 获取的数据，通过调用 JavaScript  `Fetch`  API 更新界面。

如果学习过程中有什么疑问，或者想深入地学习相关内容，请参考以下链接：

-   [Express routing documentation](https://expressjs.com/en/guide/routing.html)
-   [MDN fetch API documentation](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
-   [JavaScript Promises Introduction](https://developers.google.com/web/fundamentals/primers/promises)

## 习题资源

### 请点击链接下载“Web API 和异步应用”这一章节的习题翻译：  

[练习区翻译 - 仅习题](https://u-subs-vtt.s3.cn-north-1.amazonaws.com.cn/zh-cn/%E7%BB%83%E4%B9%A0%E5%8C%BA%E7%BF%BB%E8%AF%91+-+%E4%BB%85%E4%B9%A0%E9%A2%98.md)  
[练习区翻译 - 带答案](https://u-subs-vtt.s3.cn-north-1.amazonaws.com.cn/zh-cn/%E7%BB%83%E4%B9%A0%E5%8C%BA%E7%BF%BB%E8%AF%91+-+%E5%B8%A6%E7%AD%94%E6%A1%88.md)

# *Lesson 2 搭建Node和Express开发环境*

# Node.js 概览

[video]

在电脑上安装 Node.js 是使用它的第一步。根据你所使用的操作系统，请访问下面的链接安装 Windows 或 Mac 版的 Node.js。

[Node.js 下载页面](https://nodejs.org/en/download/)

如果你的电脑上已经安装了 Node.js，请阅读[这篇文章](https://www.hostingadvice.com/how-to/update-node-js-latest-version/)学习如何升级。

# 使用 Node

**NPM**  是随 Node 一起预装的包管理器，它是 Node 最有用的特性之一。起先，它只是为了方便地下载和管理 Node 包。现在，它已经成为前端 JavaScript 开发的常用工具。

模块（module）是可引入项目的 JavaScript 类库，包（package）囊括了该模块的所有文件。Node.js 有成千上万的包，NPM 让你可以便捷地访问它们。该课程会频繁用到以下三个包：**Express**、**CORS**  和  **Body-Parser**。**CORS**  可以实现网页的跨域访问，**Body-Parser**  作为一种中间件，可以解析路由给服务器的数据。我们先来看一下如何使用 NPM 从命令行安装包：

[video]

下面是 NPM 安装包的命令：`npm install package-name`

如果要安装 ‘body-parser’，则执行：  `npm install body-parser`

新建  `Server.js`  文件，使用下面的代码将刚安装的包引入：  `var bodyParser = require('body-parser')`

只需要把文件路径传入，Node 就可以调用  `require()`  函数引入相应的包。

### 延伸阅读

-   如果想了解更多有关 Node.js 的信息，请访问  [Node 官网](https://nodejs.org/en/)，或者[在 Twitter 上关注 @node.js](https://twitter.com/nodejs)。
-   请访问  [NPM 官网](https://www.npmjs.com/)  学习更多有关 NPM 的内容。

# Express 概览

在终端上运行  `npm install express`  命令安装 Express。然后使用下面的代码创建一个 Web 应用实例：

```
// Express to run server and routes
const express = require('express');

// Start up an instance of app
const app = express();

```

[video]

新建一个  `server.js`  文件，首先引入  `express`，然后初始化一个 Web 应用实例。一旦使用 Express 生成实例，便可以使用  `.use()`  方法把 app 和 其他软件包关联起来。Express 4 及以上版本需要使用  `body-parser`  中间件处理  `POST`  请求。它原本是 Express 框架的内置组件，但是现在需要单独安装。下面的例子展示了如何在 app 中关联  `body-parser`  和  `cors`  包。

```
/* Dependencies */
const bodyParser = require('body-parser')
/* Middleware*/
//Here we are configuring express to use body-parser as middle-ware.
app.use(bodyParser.urlencoded({ extended: false }));
app.use(bodyParser.json());
// Cors for cross origin allowance
const cors = require('cors');
app.use(cors());
```

我们已经学会了如何使用 Express 创建 Web 应用实例，并且在应用中引入其他 Node 包，但是路由功能才把 Express 的功能发挥到极致。在深入学习路由之前，我们先需要弄清楚什么是服务器，并且学会在本地创建一个服务器来开发 Web 应用。

### 延伸阅读

请访问  [MDN web docs page](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/Introduction)  了解更多有关 Node 和 Express 的知识。

### `cors`、`urlencoded`  和  `json`  是干什么的？

我们并不会深入学习  `cors`、`urlencoded`  和  `json`，如果你想了解更多，请访问下面的链接：

-   [Cross-origin resource sharing (CORS)](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing)  和  [Express documentation for CORS](https://expressjs.com/en/resources/middleware/cors.html)
-   [URL Encoding](https://en.wikipedia.org/wiki/Percent-encoding)  和  [Express documentation for  `bodyParser`’s  `urlencoded`  functionality](https://github.com/expressjs/body-parser#bodyparserurlencodedoptions)
-   [JavaScript Object Notation (JSON)](https://en.wikipedia.org/wiki/JSON)  和  [Express documentation for  `bodyParser`’s  `json`  functionality](https://github.com/expressjs/body-parser#bodyparserjsonoptions)

# 使用 Node 和 Express 创建本地服务器

[video]

还可以使用箭头函数实现同样功能，下面的例子是经箭头函数改写之后的代码：

```
const server = app.listen(port, ()=>{console.log(`running on localhost: ${port}`)})
```

# 创建本地服务器 - 第 2 部分

由于是开发服务器端代码，`console.log`  会在终端运行，而不是像之前熟悉的那样，在浏览器里运行。请看下面的视频演示：

[video]

# 服务器端目录结构

[video]

视频中的所有文件都放在项目主目录，也叫做根目录下。一旦这样设定项目的目录结构，就只需要在  `server.js`  中编写一行代码，将路径指向包含  `index.html`  和其他静态页面的目录。在视频中，这个目录是  `website`，因此需要在  `server.js`  添加下面一行代码：

`app.use(express.static('website'));`

这行代码关联了服务器端代码（`server.js`  中的代码）和客户端代码（存放在  `website`  目录中的代码）。

本节课讲述了如何创建服务器，并在本地运行 Web 应用，我们还谈到了项目的目录结构。下一节课我们会讲解路由。

### 延伸阅读

访问  [Express 官网](https://expressjs.com/)学习更多有关 Express 的知识，特别是这个  [简单的 Express 服务器示例](https://expressjs.com/en/starter/hello-world.html)。


# *Lesson 3 HTTP请求和路由*

[video]

下面的示例代码中，使用  `app.get()`  处理 GET 请求。第一个参数是 URL——这里使用项目主页的地址，第二个参数是一个回调函数。在这个函数里，使用  `.send()`  方法发回响应，这个例子中，响应就是一条信息 'hello world'。程序运行起来后，每当在浏览器里访问项目主页，就会向服务器发起一次 GET 请求，响应返回后，将 'hello world' 显示在用户的屏幕上。

```
var express = require('express')
var app = express()

// respond with "hello world" when a GET request is made to the homepage
app.get('/', function (req, res) {
  res.send('hello world')
})
```

# GET 请求进阶

这个 Hello world 小程序固然工作得很好，但是 GET 请求还可以返回更有用的数据。比如我们想要一个存储用户信息的 JavaScript 对象。

-   在示例代码中，我们使用  `const appData = {}`  创建了一个空的 JavaScript 对象。变量  `appData`  持有应用数据，后面我们还会使用 POST 请求向它发送数据。但是现在当收到 GET 请求后，我们只是简单的返回该对象就够了。

```
var express = require('express')
var app = express()
// Create JS object
const appData = {}
// Respond with JS object when a GET request is made to the homepage
app.get('/all', function (req, res) {
  res.send(appData)
})

```

这个示例中，我们创建了一条新路由：'/all'。当访问 'localhost:3000/all' 时就会触发 GET 请求，返回定义好的 JavaScript 对象。

-   注意，处理 GET 请求的回调函数有两个参数：`req`  和  `res`，你也可以给它们起其他名字。每个 GET 请求都会生成一个 request 对象，它包含了所有请求数据，同时生成一个 response 对象，作为 GET 请求的响应返回。下面是一条 GET 请求包含的信息列表：

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/029988b1-03ff-41ab-8084-662b2f360082/modules/bd3c5e28-279d-4fab-95af-d90dabb4cc19/lessons/f1b56940-804a-4b26-9ce0-ec3efa25be28/concepts/0fb536c7-a360-4cbc-b480-f4d4606b0fa3#)

![一条 GET 路由的 `req` 参数包含的部分信息。](https://video.udacity-data.com/topher/2019/July/5d23afd9_get-data/get-data.png)

一条 GET 路由的  `req`  参数包含的部分信息。

## 路由和 GET 请求练习

向  `app`  实例添加一条 GET 路由：‘/data’，返回字符串 ‘welcome!’。传入回调函数的两个参数分别是：`req`  和  `res`。

提交

Show Solution

```
app.get('/data', function (req, res) {
  res.send('welcome!');
});
```

## 路由和 GET 请求练习 2

GET 和 POST 路由的回调函数经常使用  `(req, res)`  和  `(request, response)`  命名它们的参数。你觉得哪一种命名方式更好？如果你需要在一段时间内输入它们几十次，哪种方式更好？你可以给它们任意起名，关键要起得有意义，输入起来高效。

提交

### 扩展阅读

本节课学习了使用 Node 和 Express 定义路由，处理 GET 请求。 请访问  ['Routing' 手册](https://expressjs.com/en/guide/routing.html)  了解更多内容。

# 路由：POST 请求

使用 HTTP POST 请求可以收集用户数据。和  `.get()`  方法类似，Express 有一个  `.post()`  方法用来处理 HTTP POST 请求。服务器端收到 HTTP POST 请求发送来的数据后将它们保存起来，后续的 GET 请求就可以拿到这些数据，这是我们上节课学过的内容。下面的代码展示了一个简单的 POST 请求：

```
// POST method route
app.post('/', function (req, res) {
  res.send('POST received')
})
```

[video]

下面我们讲一下如何配置一个简单的 POST 路由。

首先，创建一个数组保存数据：

```
const data = []

```

然后传入 URL 和回掉函数创建 POST 路由：

```
app.post('/addMovie', addMovie )

```

在回调函数中，将  `request.body`  中的数据保存到数组。我们前面看到  `request`  参数包含的数据很多，然而在这里我们真正感兴趣的只是这一点信息。

```
function addMovie (req, res){
   console.log(req.body)
   data.push(req.body)
}

```

下一节我们会介绍如何在客户端发起 POST 请求。

### 习题 1/2

请选出对 Express 路由和 HTTP 请求描述正确的所有选项：

-   Express 路由需要在服务器端设置。
    
-   Express 提供了和 HTTP 请求一一对应的方法，比如 GET 和 POST。
    
-   GET 请求可以保存应用数据。
    
-   GET 和 POST 请求可以在 API 和 服务器之间存取数据。
    

提交

提示：四选三。1/2/4

## 路由和 POST 请求练习 2

编写一条 POST 路由：`’/flavor’`，为喜欢的冰淇淋增加新口味，并将它保存在  `data`  数组中。

```
const data = [];
// Complete the POST route started for you by adding the route as the first parameter below:
app.post(_,addFlavor);
function addFlavor(req,res){
// And by adding the body of the request to the `data` array on the line below

};

```

提交

Show Solution

```
const data = [];
app.post('/flavor', addFlavor);

function addFlavor (req, res) {
  data.push(req.body);
};
```

那么 POST 路由是如何激活的？它从哪里得到的数据？答案将会在下一节课揭晓。下节课我们会将客户端和服务器端代码关联起来，学习如何在浏览器中 GET 和 POST 数据。

# 认识服务器和客户端代码

[video]

在  `server.js`  中我们配置了 POST 路由，现在把视线转入  `website`  目录，在  `app.js`  中编写客户端代码。下面的代码发起了一个 POST 请求：

```
const postData = async ( url = '', data = {})=>{
    console.log(data);
      const response = await fetch(url, {
      method: 'POST', 
      credentials: 'same-origin',
      headers: {
          'Content-Type': 'application/json',
      },
     // Body data type must match "Content-Type" header
      body: JSON.stringify(data), 
    });

      try {
        const newData = await response.json();
        console.log(newData);
        return newData;
      }catch(error) {
      console.log("error", error);
      }
  }

postData('/add', {answer:42});

```

下一节展示了这个过程。

# 服务器客户端示例

[video]

让我们关注 POST 请求，这是传入  `fetch()`  方法的第二个参数，第一个参数是请求地址。

```
 {
      method: 'POST', 
      credentials: 'same-origin',
      headers: {
          'Content-Type': 'application/json',
      },
      body: JSON.stringify(data),
 }

```

credentials 和 headers 是成功发起一个 POST 请求的必要部分，这里需要注意  `Content-Type`，大多数情况下，我们都把它设置为 JSON。

重点来了：因为要访问 POST 路由，所以  `method`  应设置为  `POST`。如果访问  `GET`  路由，则  `method`  应设置为  `GET`。我们对请求的  `body`  部分最感兴趣，这是服务器端获取数据的地方。客户端以字符串的形式向服务器端发送数据，使用  `JSON.stringify()`  可以把 JavaScript 对象转换为字符串，这里是吧  `data`  转换成字符串。

### 练习题

选出所有关于客户端和服务器端编程的正确描述：

~~-   服务器端和客户端代码在同一个文件里。~~
    
-   服务器端代码和客户端代码需要在不同的文件中编写，在项目中存放在各自的目录下。
    
-   服务器端创建的路由，可以在客户端使用 GET 或 POST 请求访问。
    
-   服务器端不依赖于浏览器管理路由数据。

# 处理 POST 请求

我们已经学会了如何从客户端发送 POST 请求，接下来回到服务器端，学习如何处理 POST 请求中的数据。在前面的例子中，我们在最后一行代码中调用了  `postData`  函数，传入 POST 路由的 URL 和 POST 数据，像下面这样：  `postData('/add', {answer:42})`

在服务器端代码中，我们就能拿到数据  `answer:42`。在上一个例子中，我们把数据绑定在 POST 请求的  `body`  字段中，因此在服务器端，使用  `request.body`  获取数据。

这里我们定义变量  `data`  来存放  `request.body`  中的数据，然后将它打印出来：

```
app.post('/add', function (request, response) {
    let data = request.body;
    console.log(data);
});

```

在终端中输出如下：  `{answer:42}`

只是把数据打印出来并没有什么用，要处理 POST 请求，需要把收到的数据保存在服务器端。在本例中，可以使用下面的语句将数据赋给变量  `projectData`:

`projectData["x"] = y`

这行代码给 JavaScript 对象增加了一个属性  `"x"`，它的值是  `y`。假设 POST 请求中的数据是  `{intelligence:100}`，使用下面的代码把它保存在一个新属性中：  `let data = request.body; projectData["intelligence"]= data.intelligence;`

注意这里使用  `"intelligence"`  定义新属性，使用  `data.intelligence`  提取数据。请访问  [MDN Web Docs 属性访问操作](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Property_accessors)  获取更多内容。

### 习题 1/2

```
const data = [{animal:"elephant", score: 10},{animal:"kangaroo",score:3}]

function makeData(request){

}

makeData({body:{animal:"turtle", score:7}})

```

为函数  `makeData`  填入下面哪种代码，可以为数组  `data`  添加新的元素，并且遵循已有元素的结构？

-   ```
    let newData = request;
    let newEntry =     
        animal: newData.animal,
        score: newData.score
    data.push(newEntry)
    ```
    
- 正确  ```
    let newData = request.body;
    let newEntry = {
        animal: newData.animal,
        score: newData.score
        }    
    data.push(newEntry)
    
    ```
    

提交

## 客户端和服务器端代码练习

假设客户端代码通过  `postData()`  函数发起 POST 请求，向服务器端发送数据  `{answer:42}`。编写服务器端代码，将请求中的数据赋给对象  `projectData`。

```
...
projectData = [];
app.post('/add', function(request, response){
  // Your code goes here   
}) 

```

提交

显示答案

```
projectData.push(request.body);
```

本节课学习了服务器和客户端代码如何协同工作，在 Web 应用间传递数据。我们学习了如何在服务器端配置 POST 路由，然后在客户端发起 POST 请求。我们还学习了如何结构化存放 POST 请求中的数据。下节课我们会学习异步函数，并且深入学习示例程序中出现的一些语法，比如：`async`、  `await`、  `try`  和  `catch`  等。

请访问  [Stack Overflow 上这篇帖子](https://stackoverflow.com/questions/1404376/what-is-client-side-javascript-and-what-is-server-side-javascript)  了解更多有关服务器端和客户端编程的内容。

# *Lesson 4 异步 JavaScript*

# 异步 JavaScript

JavaScript 是一门单线程编程语言，也就是说代码是在同一线程内，从上到下、依次运行。

在特定场景下使用异步编程是 Web 开发者必备的技能。JavaScript 提供了多种用于异步编程的工具，`setTimeout()`  函数是最常见的一个，它让代码打破常规，不必逐行按顺序运行。让我们通过下面的视频，了解它是怎样工作的：

最后调用 console.log("second")

and then we console.log a string second.

[video]

# Promises

JavaScript 提供了很多用于异步编程的工具，比如：setTimeout()、AJAX 等。最近 JavaScript 又原生支持了 Promises，人们普遍认为它是编写异步程序的最佳工具。

可以把 Promises 想象成一种特殊的函数，在任务执行成功(resolve) 或失败(reject) 后采取相应的操作， 操作本身会拿到任务成功（'resolved'）或失败（'reject'）后的数据做进一步处理。

下面是 Promise 对象的定义：

```
var promise = new Promise(function(resolve, reject) {
  // do a thing, possibly async, then…

  if (/* everything turned out fine */) {
    resolve("Stuff worked!");
  }
  else {
    reject(Error("It broke"));
  }
});

```

有很多种执行异步任务的方法，Promises 艳压群芳。它灵活、语法友好、处理错误方式更简单。Promises 是 JavaScript 提供的一件趁手工具，但是它需要额外的模板代码，这种情况直到 ES2017 (ES8) 中才会改善。多亏 JavaScript 新增了对原生  `async`  的支持，让我们可以很容易写出异步代码。

要在函数中异步调用  `fetch()`  或其他方法，必需使用 JavaScript 提供的关键字。请看下面的例子，它将前面的例子改写成了异步调用：

```
const postData = async ( url = '', data = {})=>{
    // console.log(data)
      const response = await fetch(url, {
      method: 'POST', // *GET, POST, PUT, DELETE, etc.
      credentials: 'same-origin', // include, *same-origin, omit
      headers: {
          'Content-Type': 'application/json',
      },
      body: JSON.stringify(data), // body data type must match "Content-Type" header        
    });

      try {
        const newData = await response.json();
        console.log(newData);
        return newData
      }catch(error) {
      console.log("error", error);
      // appropriately handle the error
      }
  }

  postData('/addMovie', {movie:' the matrix', score: 5})

```

`postData`  是一个异步箭头函数，在最后一行传入参数并调用。在函数定义前加  `async`  是定义异步函数的关键，一旦使用 'async' 定义函数，就可以使用  `await`、`try`  和  `catch`  处理 Promise 成功或失败的情形，比如成功发送 POST 请求。当后续操作需要上次操作的返回值时，使用  `await`  关键字。好像在告诉程序，先等一会儿，等这个弄完了才轮到你——这便是异步 JavaScript 的魔力所在。

### 练习题

下列有关异步 JavaScript 的描述中，哪些是正确的？提示：五选三。

-   ~~异步 JavaScript 是不可能完成的任务——想都别想！~~
    
-   JavaScript 原生支持 Promises，当条件满足时可以异步调用。
    
-   使用  `async`  关键字，就可以把 JavaScript 函数变成异步函数。
    
-   使用  `async`  关键字定义异步函数后，就可以使用  `await`、`try`、`catch`  方便地编写异步代码。
    
-   ~~JavaScript 本来就是异步运行的，在方法前使用  `await`  就可以让每个方法异步执行。~~
    

提交

下一节课我们会使用 JavaScript 异步 fetch 函数访问 Web API，领略前端开发的动态魅力。

### 延伸阅读

阅读[这篇文章](https://developers.google.com/web/fundamentals/primers/promises)  了解更多有关 Promises 的内容。

# 使用异步 Fetch 函数访问 Web API

[video]

# 用户凭证和 API 密钥

很多 Web API 需要注册获取用户凭证后，使用 API 密钥向服务器端发起请求。

[video]

如果访问 [NASA’s API documentation](https://api.nasa.gov/)，就会发现需要注册获取 API 密钥后，才能发起请求。

# 给代码添加 Fetch

[video]

下面的客户端代码向动物信息 API 发起一个 GET 请求：

```
let baseURL = 'http://api.animalinfo.org/data/?animal='
let apiKey = '&appid=9f15e45060...';

document.getElementById('generate').addEventListener('click', performAction);

function performAction(e){
const newAnimal =  document.getElementById('animal').value;
getAnimal(baseURL,newAnimal, apiKey)

}
const getAnimal = async (baseURL, animal, key)=>{

  const res = await fetch(baseURL+animal+key)
  try {

    const data = await res.json();
    console.log(data)
    return data;
  }  catch(error) {
    console.log("error", error);
    // appropriately handle the error
  }
}
```

# 异步 Fetch Web API 示例

[video]

JavaScript Fetch API 提供了一种更优雅的方式和语法发起 HTTP 请求，使用它访问 Web API 非常方便。接下来，我们会学习如何将 Fetch 调用链接起来，动态更新应用界面。

### 习题 1/2

下面哪些步骤和异步调用 Web API 有关？提示：五选四。

-   在提供 Web API 的网站注册并获取用户凭证。
    
-   创建变量保存 Web API 地址和 API 密钥。
    
-   ~~使用  `setTimeout`  函数等待 Web API 请求返回，然后执行后续操作。~~
    
-   构建动态 URL 访问 Web API。
    
-   在  `async`  函数内使用 Fetch 向 Web API 发起 GET 请求。
    

提交

## Async Fetch w/ Web APIs Quiz 2

以  `www.api.com/data?`  为基准，创建动态 URL，使用变量  `holder`  保存用户输入，API 密钥为  `68`。

提交

显示答案

```
'www.api.com/data?='+holder+68
```

JavaScript Fetch API 提供了一种更优雅的方式和语法发起 HTTP 请求，使用它访问 Web API 非常方便。接下来，我们会学习如何将 Fetch 调用链接起来，动态更新应用界面。

-   [Fetch over view on MDN](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
-   [Using Fetch on MDN](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)

# Promises 链 - 相互依赖的 GET 和 POST 请求

[video]

在使用 fetch 发起异步 GET 请求时，我们用到一个辅助方法。

在  `.then()`  函数中，我们可以调用另一个异步函数发起一个 POST 请求，将数据保存在应用中。假设服务器端已经有这样一条 POST 路由，那么就可以在客户端传入 URL 和数据，使用同样的方式发起 POST 请求。我们需要使用返回数据和从 DOM 中获得的数据构建请求体，这会麻烦一点儿，但也是乐趣所在。

回顾一下，需要为  `postData()`  函数传入两个参数：一个 URL，一个存储数据的对象。我们从前一次 fetch 的响应中取回数据，并将它赋给新对象，如下所示：

`postData('/addAnimal', {animal:data.animal, fact: data.fact} )`

我们还希望加入一些和动物有关的趣事，这些信息可以从用户输入的文本框中获得。发送 POST 请求的最终代码如下，它将这些数据保存在应用中：

`postData('/addAnimal', {animal:data.animal, fact: data.fact, fav:favFact} )`

在服务器端接收到请求后，使用下面的代码保存数据：

```
app.post('/addAnimal', addAnimal);

function addAnimal(req,res){

  newEntry = {
    animal: req.body.animal,
    facts: req.body.fact,
    fav: req.body.fav
  }

  animalData.push(newEntry)
  console.log(animalData)
}

```

让我们通过一个例子

So let's see an example of what it looks like to chain

Play Video

### 练习题

下面有关 Promises 的描述，哪些是正确的？

-   ~~Promises 嵌套是一项最佳实践。~~
    
-   使用  `.then()`  函数链接 Promises 可以发起多次有依赖关系的 HTTP 请求。
    

提交

恭喜！终于到了学习如何使用请求中的数据更新用户界面的时候了！

# 动态更新用户界面

Play Video

下面的代码演示了如何使用链接在一起的 GET 和 POST 请求从 Web API 获取数据，并更新 DOM 元素的过程：

HTML

```
<label for="animal">Enter the name of your favorite animal</label>
<input id="animal" name="animal">
<textarea id="favorite" placeholder="Enter your favorite thing about your favorite animal" rows="9" cols="50"></textarea>
<button id = "generate">GO</button>

```

JS

```
document.getElementById('generate').addEventListener('click', performAction);

function performAction(e){
  const newAnimal =  document.getElementById('animal').value;
  const favFact =  document.getElementById('favorite').value;

  getAnimal('/animalData',)
  // New Syntax!
  .then(function(data){
    // Add data
    console.log(data);
    postData('/addAnimal', {animal:data.animal, fact: data.fact, fav:favFact} );
  })
  .then(
    updateUI()
  )
}

const updateUI = async () => {
  const request = await fetch('/all');
  try{
    const allData = await request.json();
    document.getElementById('animalName').innerHTML = allData[0].animal;
    document.getElementById('animalFact').innerHTML = allData[0].facts;
    document.getElementById('animalFav').innerHTML = allData[0].fav;

  }catch(error){
    console.log("error", error);
  }
}

```

注意我们在最后调用函数更新了用户界面，那是因为更新界面的数据需要其他函数返回结果后才能拿到。我们要等到所有 Promise 成功返回后才能更新界面。现在你可以理解为什么 Promises 和 Fetch API 在异步 JavaScript 编程中如此重要的原因了吧？



<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE4MDk0MjQ2Nl19
-->
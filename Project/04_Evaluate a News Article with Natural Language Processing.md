> Build Tools and Single Page Web Apps

# Project Summary

**使用自然语言处理评估新闻文章**

The goal of this project is to give you a taste of the environment and tools you will most likely come across in a front end role. Your focus should be to understand the role every tool and technology is playing in the overall architecture, but you shouldn’t feel the need to memorize the particular commands, config setups, or structure that we create here. Every company - and even every project - will have its own custom setup, but if you understand the moving pieces you will be able to get the gist of even far more complicated projects than this one.

### What You Will Build

We will be building web tool that allows users to run Natural Language Processing (NLP) on articles or blogs found on other websites. Using an exciting new api called  [Aylien](https://aylien.com/), we can build a simple web interface to interact with their NLP system. This tool will give us back pertinent information about the article, like whether the content is subjective (opinion) or objective (fact-based) and whether it is positive, neutral, or negative in tone.

Node and express will be the webserver and routing, and webpack will be our build tool of choice. Using webpack, we will set up the app to have dev and prod environments, each with their own set of tools and commands.

### More About Natural Language Processing

NLP is considered its own branch of computer science, focused on computers’ ability to process and even interact with natural human speech. Machine learning and deep learning are used on massive amounts of data to obtain the rules and understanding of nuance in human speech. Everyone who has used Alexa or Google Assistant or other voice command systems knows that they are always improving - but they aren’t perfect. Verbal interactions can be incredibly hard to decipher. Sarcasm, for instance, requires understanding not just words and grammar but tone as well, and regional accents and ways of saying things have to be taken into account, not to mention coverage for all the major languages.

# Project Instructions

[This repo](https://github.com/udacity/fend/tree/refresh-2019)  is your starter code for the project (clone the specific branch 'refresh-2019' or download the ZIP file), although feel free to start from scratch! It is the same as the starter code we began with in lesson 2. Install and configure Webpack just as we did in the course. Feel free to refer to the course repo as you build this one, and remember to make frequent commits and to create and merge branches as necessary!

The goal of this project is to give you practice with:

-   Setting up Webpack
-   Sass styles
-   Webpack Loaders and Plugins
-   Creating layouts and page design
-   Service workers
-   Using APIs and creating requests to external urls

On top of that, I want to introduce you to the topic of Natural Language Processing. NLPs leverage machine learning and deep learning create a program that can interpret natural human speech. Systems like Alexa, Google Assistant, and many voice interaction programs are well known to us, but understanding human speech is an incredibly difficult task and requires a lot of resources to achieve. Full disclosure, this is the Wikipedia definition, but I found it to be a clear one:

> Natural language processing (NLP) is a subfield of computer science, information engineering, and artificial intelligence concerned with the interactions between computers and human (natural) languages, in particular how to program computers to process and analyze large amounts of natural language data.

You could spend years and get a masters degree focusing on the details of creating NLP systems and algorithms. Typically, NLP programs require far more resources than individuals have access to, but a fairly new API called Aylien has put a public facing API in front of their NLP system. We will use it in this project to determine various attributes of an article or blog post.

## Getting started

It would probably be good to first get your basic project setup and functioning. Follow the steps from the course up to Lesson 4 but don't add Service Workers just yet. We won't need the service workers during development and having extra caches floating around just means there's more potential for confusion. So, fork this repo and begin your project setup.

Remember that once you clone, you will still need to install everything:

`cd`  into your new folder and run:

-   `npm install`

## Setting up the API

The Aylien API is perhaps different than what you've used before. It has you install a node module to run certain commands through, it will simplify the requests we need to make from our node/express backend.

### Step 1: Signup for an API key

First, you will need to go  [here](https://developer.aylien.com/signup). Signing up will get you an API key. Don't worry, at the time of this course, the API is free to use up to 1000 requests per day or 333 intensive requests. It is free to check how many requests you have remaining for the day.

### Step 2: Install the SDK

Next you'll need to get the SDK. SDK stands for Software Development Kit, and SDKs are usually a program that brings together various tools to help you work with a specific technology. SDKs will be available for all the major languages and platforms, for instance the Aylien SDK brings together a bunch of tools and functions that will make it possible to interface with their API from our server and is available for Node, Python, PHP, Go, Ruby and many others. We are going to use the Node one, the page is available  [here](https://docs.aylien.com/textapi/sdks/#sdks). You get 1000 free requests per day.


### Step 3: Require the SDK package

Install the SDK in your project and then we'll be ready to set up your server/index.js file.

Your server index.js file must have these things:

-   [ ] Require the Aylien npm package
    
    ```
    var aylien = require("aylien_textapi");
    
    ```
    

### Step 4: Environment Variables

Next we need to declare our API keys, which will look something like this:

```
// set aylien API credentias
var textapi = new aylien({
  application_id: "your-api-id",
  application_key: "your-key"
});

```

...but there's a problem with this. We are about to put our personal API keys into a file, but when we push, this file is going to be available PUBLICLY on Github. Private keys, visible publicly are never a good thing. So, we have to figure out a way to make that not happen. The way we will do that is with environment variables. Environment variables are pretty much like normal variables in that they have a name and hold a value, but these variables only belong to your system and won't be visible when you push to a different environment like Github.

-   [ ] Use npm or yarn to install the dotenv package  `npm install dotenv`. This will allow us to use environment variables we set in a new file
-   [ ] Create a new  `.env`  file in the root of your project
-   [ ] Go to your .gitignore file and add  `.env`  - this will make sure that we don't push our environment variables to Github! If you forget this step, all of the work we did to protect our API keys was pointless.
-   [ ] Fill the .env file with your API keys like this:
    
    ```
    API_ID=**************************
    API_KEY=**************************
    
    ```
    
-   [ ] Add this code to the very top of your server/index.js file:
    
    ```
    const dotenv = require('dotenv');
    dotenv.config();
    
    ```
    
-   [ ] Reference variables you created in the .env file by putting  `process.env`  in front of it, an example might look like this:
    
    ```
    console.log(`Your API key is ${process.env.API_KEY}`);
    
    ```
    
    ...Not that you would want to do that. This means that our updated API credential settings will look like this:
    
    ```
    // set aylien API credentials
    // NOTICE that textapi is the name I used, but it is arbitrary.
    // You could call it aylienapi, nlp, or anything else, 
    //   just make sure to make that change universally!
    var textapi = new aylien({
    application_id: process.env.API_ID,
    application_key: process.env.API_KEY
    });
    
    ```
    

### Step 5: Using the API

We're ready to go! The API has a lot of different endpoints you can take a look at  [here](https://docs.aylien.com/textapi/endpoints/#api-endpoints). And you can see how using the SDK simplifies the requests we need to make.

I won't provide further examples here, as it's up to you to create the various requests and make sure your server is set up appropriately.

## After the Aylien API

Once you are hooked up to the Aylien API, you are most of the way there! Along with making sure you are following all the requirements in the  [project rubric](https://review.udacity.com/#!/rubrics/2668/view), here are a few other steps to make sure you take.

-   Parse the response body to dynamically fill content on the page.


    
-   Test that the server and form submission work, making sure to also handle error responses if the user input does not match API requirements.
 You should add  [Jest](https://jestjs.io/en/)  to your project to handle testing as well.
    
-   Go back to the web pack config and add the setup for service workers. 

    
-   Test that the site is now available even when you stop your local server

    

Need a refresher on writing unit tests? Check out these resources:

-   [Jest Documentation](https://jestjs.io/docs/en/getting-started)
-   [Jest Tutorial for Beginners](https://www.valentinog.com/blog/jest/)

## Deploying

A great step to take with your finished project would be to deploy it! Unfortunately its a bit out of scope for me to explain too much about how to do that here, but checkout  [Netlify](https://www.netlify.com/)  or  [Heroku](https://www.heroku.com/)  for some really intuitive free hosting options.

# Project Submission: Evaluate a News Article with Natural Language Processing

This project requires you to build a web tool that allows users to run Natural Language Processing (NLP) on articles or blogs found on other websites.

## Rubric

Your project will be evaluated by a Udacity code reviewer according to the  [project rubric](https://review.udacity.com/#!/rubrics/2668/view). Please make sure to re-review the rubric for detailed project requirements prior to submission.

## Submission

Once you've met all of the rubric requirements, you can submit your project as either a zip file or a Github repository link.

# 项目概述

此次项目旨在熟悉前端中最有可能遇到的环境和工具。你的重点应该是了解每种工具和技术在总体架构中扮演的角色，但并不需要记住此处创建的特定命令、配置或结构。每个公司 — 甚至每个项目 — 都会有自己的自定义设置。不过如果你理解这些可变的部分，能有更多收获。

### 我将构建什么？

你将构建一个 Web 工具，使用户可以在其他网站上的文章或博客上运行自然语言处理（NLP）。使用新 API —  [Aylien](https://aylien.com/)，我们可以构建一个简单的 Web 界面来与其 NLP 系统进行交互。该工具会提供有关文章的相关信息，比如内容是偏主观（意见）还是偏客观（基于事实）；内容是正面、中性还是负面。

使用 Node 和 Express 作为 Web 服务器和路由，使用 webpack 构建工具。用 webpack 将应用程序设置为具有开发和生产环境，每个环境都有自己的一套工具和命令。

### 自然语言处理相关说明

自然语言处理（NLP）是计算机科学的一个分支，专注于计算机处理自然人类语言甚至与之互动的能力。对大量数据应用机器学习和深度学习，来获取规则和对人类语言细微差别的理解。只要是使用过 Alexa 或 Google 助手或其他语音命令系统的人，都能知道它们一直在进步 — 但并不完美。语音互动可能尤其难以解释，比如，讽刺不仅需要理解单词和语法，还需要理解语调，并且必须考虑地域口音和表达方式，更不用说还要覆盖所有主要语言了。

# 项目说明

可以使用[这个代码库](https://github.com/udacity/fend/tree/refresh-2019)作为项目的初始代码（克隆这个专门的分支：'refresh-2019'，或者下载 zip 文件），当然也可以从零开始开发！初始代码与课程第 2 节开始时的代码相同。按照课程所学，安装并设置 webpack，可以随时参考课程代码库。记得要多提交，必要时创建或合并分支。

此次项目的目的是实践：

-   设置 Webpack
-   Sass 样式
-   Webpack 加载器和插件
-   设计页面和创建布局
-   Service Worker
-   使用 API，创建对外部 url 的请求

最重要的是，我想向你介绍自然语言处理这一主题。NLP 利用机器学习和深度学习来创建可以解释自然语言的程序。诸如 Alexa、Google 助手之类的系统以及许多语音交互程序对我们来说是很熟悉的，但是了解人类语言是一项非常困难的任务，并且需要大量资源来实现。以下是维基百科的定义，说的比较清楚：

> 自然语言处理（Natural Language Processing，缩写 NLP）是计算机科学、信息工程、人工智能和语言学领域的分支学科。此领域探讨计算机与自然语言的互动、主要研究如何对计算机进行编程来处理和分析大量自然语言数据。

你可能需要花费数年时间研究 NLP 系统和算法，才能获得 NLP 硕士学位。通常，NLP 程序需要的资源远远超过个人能够访问的资源，但是这个最新的 API — Aylien，将它们的 NLP 系统公布于众，供所有人使用。我们将在此项目中使用这一 API 来确定文章或博客的各种属性。

## 开始

项目开始的设置和基础功能的运行应该不会有什么问题。请按照课程中学过的步骤进行操作（直到第 4 节之前），暂时先不要添加 Service Worker。在开发过程中，我们并不需要 Service Worker，并且多余的缓存反而会容易造成混乱。那么，首先请复刻代码库并开始项目设置。

记住，克隆代码库之后，你仍然需要安装所有需要的工具：

`cd`  到新的项目文件夹，运行

-   `npm install`

## 设置 API

Aylien API 可能与以前使用的 API 不同，它为你安装了一个 node 模块来运行某些命令，这会简化我们从 node/express 后端发出的请求。

### 步骤 1：注册获取 API 密钥

首先，你需要打开[这个页面](https://developer.aylien.com/signup)，注册后会获得一个 API 密钥。不用担心，在学习本课程时，该 API 每天可以免费使用多达 1000 个请求或 333 个密集请求。你可以免费检查当天剩余的请求数量。

### 步骤 2：安装 SDK

接下来，你需要获取 SDK。SDK 是 Software Development Kit 的缩写，表示软件开发工具包。SDK 通常是一个程序，将各种工具结合在一起，帮助你使用特定技术。SDK 会适用于所有主要语言和平台。比如 Aylien SDK 就汇集了许多工具和功能，使我们可以从自己的服务器与 API 进行接口，并且可用于 Node、Python、PHP、Go、Ruby 和许多其他语言。我们要使用的是 Node 版本，该页面位于[此处](https://docs.aylien.com/textapi/sdks/#sdks)，每天可以获得 1000 个免费请求。

### 步骤 3：引入（require）SDK 包

在你的项目中安装 SDK，然后就可以设置 server/index.js 文件了。

你的 server/index.js 文件中必须包含：

-   [ ] 引入 Aylien npm 包
    
    ```
    var aylien = require("aylien_textapi");
    
    ```
    

### 步骤 4：环境变量

接下来需要声明我们的 API 密钥，如下所示：

```
// set aylien API credentias
var textapi = new aylien({
  application_id: "your-api-id",
  application_key: "your-key"
});

```

但是这存在一个问题，现在的操作是将自己个人的 API 密钥写入一个文件中，但是当我们推送到 GitHub 远端时，这个文件会变成公开文件。私有密钥公开显示永远不是一件好事。所以我们要找到一种方式来避免这样的结果，该方式就是用环境变量。环境变量与普通变量非常相似，都具有名称和值，但是环境变量仅属于你自己的系统，当你推送到类似 GitHub 等其他环境时将不可见。

-   [ ] 使用 npm 或 yarn 安装 dotenv 包  `npm install dotenv`. 这个工具允许我们使用设置在一个新文件中的环境变量。
-   [ ] 在项目的根目录中，创建一个新的  `.env`  文件
-   [ ] 打开 .gitignore 文件，添加  `.env`  — 这样可以确保我们不会将环境变量推送到 GitHub，如果忘记这一步，那么为保护 API 密钥所做的所有工作都没有意义了。
-   [ ] 在 .env 文件中填入你的 API 密钥，像这样：
    
    ```
    API_ID=**************************
    API_KEY=**************************
    
    ```
    
-   [ ] 将以下代码加入到 server/index.js 文件的最顶端：
    
    ```
    const dotenv = require('dotenv');
    dotenv.config();
    
    ```
    
-   [ ] 通过在变量名之前添加  `process.env`  来引用 .env 文件中创建的变量，用法如下所示：
    
    ```
    console.log(`Your API key is ${process.env.API_KEY}`);
    
    ```
    
    ……这里并不是说你要编写上面的具体代码，只是为了表现对环境变量的调用方式，也就是说你需要将 API 凭证的设置更新为类似下面的样子：
    
    ```
    // 设置 aylien API 凭证
    // 注意 textapi 是我使用的名称，你可以使用其他名称
    // 可以将其称为 aylienapi、nlp 或其他名称
    // 只需要确保全部统一修改掉
    var textapi = new aylien({
    application_id: process.env.API_ID,
    application_key: process.env.API_KEY
    });
    
    ```
    

### 步骤 5：使用 API

这样就准备好使用 API 了！该 API 有很多不同的端点，你可以在[这里](https://docs.aylien.com/textapi/endpoints/#api-endpoints)查看。你会看到使用 SDK 如何简化需要发出的请求。

这里，我不会再提供更多示例，因为这取决于你要创建的各种请求，并且要确保正确设置了服务器。

## 设置好 Aylien API 之后，要做什么？

连接到 Aylien API 之后，你就完成了大部分工作，同时要注意满足[项目要求](https://review.udacity.com/#!/rubrics/2782/view)，以下是一些其他的检查要点。

-   解析响应主体，将其动态添加到页面
    
-   测试服务器和表单提交是否正常工作，如果用户输入不符合 API 要求，确保有处理错误的响应。你还应该将  [Jest](https://jestjs.io/en/)  添加到项目中来处理测试。
    
-   回到 webpack 配置，添加 Service Worker。
    
-   测试你的网站可以在关闭本地服务器之后正常访问。
    

## 部署

完成项目后的一个重要步骤就是部署！很遗憾，我不能在这里详细解释如何去做，这有些超出课程范围了。你可以查看  [Netlify](https://www.netlify.com/)  或者  [Heroku](https://www.heroku.com/)  了解一些非常直观易用的免费托管选择。


# 项目提交：使用自然语言处理评估新闻文章

此项目需要你构建一个 Web 工具，使用户可以在其他网站上的文章或博客上运行自然语言处理（NLP）。

## 审阅标准

优达学城的审阅专家会根据[项目要求](https://review.udacity.com/#!/rubrics/2782/view)对你的项目进行审阅，请在提交前确认已查看详细的项目要求。

## 项目提交

满足所有审阅要求后，你可以在下方提交打包后的 zip 文件或 GitHub 代码库链接。
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY4MzQ0NTg4OV19
-->
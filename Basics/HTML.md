# HTML 简介

Play Video

欢迎来到 HTML 简介。在这部分内容中，我们首先会深入了解 HTML ，它是网页的基本组成元素。接着，我们会开始学习 CSS ，通过它来给我们的页面添加样式。最后，我们会着重关注页面布局知识的学习，确保页面的所有元素按照我们预想的分布排列。

HTML 意思是超文本标记语言（HyperText Markup Language），这与我们在浏览器中 URL 开头看到的 http 中包含的“超文本”是相同的意思，是一种可被浏览器识别并渲染的语言。在课程结束后，你会学习如何使用它创建页面，就像你平时浏览的那些网页一样。

对于所有想要进行 Web 开发的人来说，HTML 是一个共同的起点。在课程后面阶段，你会把它和 CSS 结合起来，再往后，你还会和 JavaScript 结合起来，一起创造出完整的网页体验。总的来说，HTML 是网页的最基本的组成部分。

Play Video

### 一些早期的 HTML 标签

让我们快速浏览一些早期的 HTML 标签。通过 HTML标签，我们可以告诉浏览器如何在页面上显示不同的元素。尤其是在你引入 CSS 设置样式之后，可以通过标签指定一些特定的样式。这里我们会先简单介绍一些内容，后续学习 DOM 时，你会了解到更多信息。

#### `<!DOCTYPE html>`

几乎每个 HTML 文档都以这个标签开头，告诉浏览器这是 HTML 文档

#### `<html>`  &  `</html>`

第一个标签紧跟在 doctype 标记之后，第二个则是结束标签，会在文档末尾出现，说明之间所有的内容都是 HTML 代码

#### `<body>`  &  `</body>`

你在网页上看到的大部分内容是包含在 body 标签内的。使用  `<body>`  开始，使用  `</body>`  标签关闭。实际上，在正文之前可能还会有一个 部分，但是现在我们先省略掉。

下面是一个非常简短的例子，说明以上标签在实际情况中可能是什么样子，但是其中还没有加入任何内容：

```
<!DOCTYPE html>
<html>
  <body>
    <!-- Page content would go here -->
  </body>
</html>
```

# 文本编辑器

我们使用浏览器打开 HTML 文件。

用于创建 HTML 文件的程序叫做文本编辑器。文本编辑器可以创建和修改多种类型的文件，包括 HTML。还有一些更高级的文本编辑器，称为集成开发环境 (IDE) ，具有其他更多的功能。

选择一个好的文本编辑器非常重要，有助于你更快地编写代码。

### Hello World 例子

`<p>Hello World!</p>`

我们使用文本编辑器编写了以上一段代码，你可以看到代表段落的  `<p>`  和  `</p>`  标签。当我们在浏览器中打开 HTML 时，这些标签并不会直接显示，而是会被浏览器解析。浏览器看到`<p>`  和  `</p>`  标签就会知道 Hello World 是一个段落。

记住，你可以通过两种方式打开 HTML 文件：

1.  由文本编辑器打开来查看源代码
2.  由浏览器打开来解析源代码

### 推荐使用的文本编辑器

-   [Visual Studio Code](https://code.visualstudio.com/)
-   [Atom](https://atom.io/)
-   [Sublime Text](https://www.sublimetext.com/)
-   [JetBrains](https://www.jetbrains.com/)
-   [NotePad++](https://notepad-plus-plus.org/)
# 练习：创建 HTML 文件

下面，我们提供了一个实时预览工作区（Workspace），你可以通过它查看 HTML 代码的实时情况 (以后我们也会提供 CSS 版本) 。你也可以使用自己计算机上的 VS Code 之类的编辑器，但是需要和教室的开发环境一致。

首先，如果你喜欢全屏展示，你可以单击工作区底部的 “展开（Expand）” 来将工作区切换为全屏显示。 位于 /home/workspace 目录中的 Instructions.md 是说明文件，当处于全屏状态时，你依然可以查看它。

HTML 实时预览工作区结构如下 :

-   左侧是目录视图，你可以在此处查看当前目录中的任何文件，另外，你也可以单击顶部的 “+” 按钮来创建或上传文件和文件夹（这是第一次练习的提示）。
-   中间是代码窗口，你单击打开的所有文件都将显示在此处，顶部的选项卡可在打开的文件之间切换，你可以在这里编写代码；这些文件将自动保存，并在几秒钟的延迟后在右侧窗口中更新（如果正常的话）。
-   右侧是实时预览窗口，在这个工作区内，它总是默认显示 “index.html” 。

如果不会做这项练习，你可以在工作区中看到 “index-solution.html” 文件，这是解决方案。请一定在查看解决方案之前先尝试一下。你需要把它重命名为 “index.html”，否则文件不会显示在实时预览窗口中。

## 练习说明

请创建一个  `index.html`  文件，并使用段落标签  `<p>`  和  `</p>`，段落内容为："Hello World" 。关于段落标记，请阅读[这里](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)。

# 文本元素 I

Play Video

### 文本元素结构

元素的基本结构由四个关键项组成，其中一项不是必须的。

`<p class="dog-breed">Labrador Retriever</p>`

1.  开始标签标记着元素的开始。
2.  开始标签和结束标签之间的就是内容，屏幕上只会显示标签内的内容。
3.  结束标签是元素的第二个标签，标记着元素的结尾，始终带有反斜线，且跟在左尖括号后面。
4.  (不是必须的) 属性名称和值。

注意，标签始终用开括号和闭括号表示。`<>`.

_注释: 有时候左括号也叫开括号，右括号也叫闭括号。_

HTML 标签种类繁多，一共有 100 多种。

最常用的 HTML 标签主要有以下两类。

**块状元素**（Block elements）包括:

-   段落  `<p>`
-   列表:
    -   无序的列表 (即，用项目标点列出)  `<ul>`
    -   有序的列表 (即，用数字列出)  `<ol>`
-   标题: 从第一级到第六级标题  `<h1>`  -  `<h6>`
-   文章：  `<article>`
-   区域：`<section>`
-   大段引用：`<blockquote>`

内联元素（Inline elements）主要用于区分某些特定文本，赋予其特定格式和功能，比如加粗、超链接等。内联元素可以是单个字词，也可以是几个字词。

**内联元素**  有:

-   链接  `<a>`
-   斜体  `<em>`
-   粗体  `<strong>`

# 文本元素 II

Play Video

### 标题

HTML中的标题与其他媒体类型中的标题相当，例如，在期刊中，大标题通常用于引起读者的注意，在其他时候，标题用于定义材料，例如电影的标题或说明性文章。

标题是描述网页内容的主要方法，选择好的标题对于高质量的网页至关重要，也有助于提升搜索引擎结果。

HTML里有六个不同级别的标题，从`<h1>`到`<h6>`。你可以根据需要选择使用，例如需要为某个章节，某个期刊文章或其他类型的内容添加标题。

另一种看待标题的方式就是当做一本书的标题一样。

`<h1>`  标题，和书名一样，介绍了内容主题。

`<h2>`  标题，就好像章节名称一样，涵盖了网页上的主要“章节”内容。

更小一些的标题如  `<h3>`  to  `<h6>`  可用于章节的更细分的主题，就像书一样，书的章节也可以有多个细分主题。

标题按从大到小的顺序排列，共有六个级别的标题，分别是从`<h1>`到`<h6>`，其中 1 是最大的标题。

H1标签主要用于网页的大标题，对于副标题，将使用其他较低的标题标签。

----------

这是一个标题的例子：

```
<h1>Observable Universe</h1>
<h2>Milky Way Galaxy</h2>
<h3>Earth</h3>
<h4>USA</h4>
<h5>Norfolk，VA</h5>
<h6>Main Street</h6>

```

显示的结果会是：

# Observable Universe

## Milky Way Galaxy

### Earth

#### USA

##### Norfolk，VA

###### Main Street

----------

#### 标题应该对读者友好，结构完整而清晰

对于盲人或视觉障碍者，他们会使用屏幕阅读软件来解析网页上的文本。 通常，这些软件会解析标题，从一个标题跳转到另一个标题，从而对文章整体内容有更好的把握。 因此，最好不要跳过一个或多个标题级别。如果你跳过了，比如从`<h1>`直接到了`<h3>`，可能会对读者造成一些困惑。 为了保证最好的用户体验，请一定正确组织你的标题！ 👍🏽

### 段落标签

段落  `<p>`  是最常用的 HTML 元素，它们默认是块级元素，写起来也很简单。

以下是用到了段落标签的 HTML 代码 - 这些代码没有用到任何特殊格式。

```
<p>
  The sweet-faced and loving Labrador Retriever is actually one of the most
  popular dog breeds.
</p>
<p>
  Labs are extremely friendly with an easygoing and high-spirited personality
  which is great for bonding with the whole family.
</p>

```

The sweet-faced and loving Labrador Retriever is actually one of the most popular dog breeds.

Labs are extremely friendly with an easygoing and high-spirited personality which is great for bonding with the whole family.

### Span 标签

HTML  `<span>`  标签主要用于将文本分组，以便进行样式设置，参见以下代码:

```
<style>
p {
  color: black;
}
.red {
  color: red;
}
</style>
<p>
  This sentence needs some <span class=”red”>visual emphasis</span> to really bring home the point.
</p>

```

显示结果是:

This sentence needs some  visual emphasis  to really bring home the point.

在代码中，visual emphasis 放置在了 span 标签里，意味着可以有单独的样式。在例子里，它有一个 red（红色）的类名，所以 span 中的文字是红色，而其他的文字仍是黑色。

### 块状引用（Blockquotes）

块状引用可以用于标记一段引用文字。

```
<blockquote cite="https://www.wikiwand.com/en/Scooby-Doo_(character)">
  <p>Ruh-roh--RAGGY!!!</p>
  <footer>—Scooby Doo，<cite>Mystery Incorporated</cite></footer>
</blockquote>

```

> Ruh-roh--RAGGY!!!
> 
> —Scooby Doo，Mystery Incorporated

### 换行

在 HTML文件里，代码之间的间距不会影响浏览器中元素的位置。如果你想在浏览器中修改间距，需要使用 HTML 的换行元素。

```
<p>
  I jump in delight<br />
  I run off in frenzy<br />
  For now I have just realized<br />
  that the fun has arrived<br />
  the fun has begun<br />
  jumping all on one piece<br />
  almost feeling like I can't breathe<br />
  blood rushing through me<br />
  a second，a beat<br />
  I feel the air on my face<br />
  My fur rising up<br />
  Free as free as it can be<br />
  That's what you feel<br />
  When your owner has arrived<br />
</p>

```

I jump in delight  
I run off in frenzy  
For now I have just realized  
that the fun has arrived  
the fun has begun  
jumping all on one piece  
almost feeling like I can't breathe  
blood rushing through me  
a second，a beat  
I feel the air on my face  
My fur rising up  
Free as free as it can be  
That's what you feel  
When your owner has arrived  

# HTML 列表

Play Video

##### _纠正_: 在 1:46，讲师说  `<li>`  是 line item，实际上应该是 “list item”。

你可以用列表的方式组织内容。

之前我提到了两种 HTML 中的列表（无序和有序），但实际上共有三种列表类型：

1.  unordered - 无序的列表
2.  ordered - 有序的列表
3.  description - 具有键值对的列表

你可以根据需要决定使用哪一种列表。之前，我使用了有序列表因为我希望它们按照顺序展示。

这里我们不会谈论更多列表信息。建议阅读[这篇文章](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl)。

### 无序列表

如果你希望列表项没有特定的顺序，比如一堆商品列表，你可以使用无序列表标签 -  `<ul>`。

无序列表使用小圆点标记每个列表项，并使用  `<li>`  包裹每个子项。

```
<p>New puppy shopping list</p>
<ul>
  <li>Treats</li>
  <li>Dog food</li>
  <li>Leash</li>
  <li>Collar</li>
  <li>Dishes</li>
  <li>ID tag</li>
</ul>

```

显示的结果是:

New puppy shopping list

-   Treats
-   Dog food
-   Leash
-   Collar
-   Dishes
-   ID tag

### 有序列表

有序列表  `<ol>`  类似于无序列表，不同之处在于每个列表有自己的编号。

当你需要列出流程的具体步骤，或者是给列表排名时，有序列表就比较有用。

和无序列表一样，你使用  `<li>`  标签包裹每个子项。

```
<p>Steps after adopting a puppy</p>
<ol>
  <li>Spoil the puppy</li>
  <li>Be happy with your puppy</li>
  <li>Repeat</li>
</ol>

```

显示的结果是:

Steps after adopting a puppy

1.  Spoil the puppy
2.  Be happy with your puppy
3.  Repeat

浏览器会自动为每个列表编号，你不需要在代码里指定编号。

# 属性

Play Video

所有 HTML 元素都可以拥有属性。属性提供了元素的额外信息，而且总是在开始标签中指定。

属性通常以键/值对的形式出现，例如`name="value"`。

以下是一些常用的属性。

### 图片

-   通常使用  `src`  属性指定图片的来源。
-   图片的替代文字通常使用  `alt`  属性指定。
-   图片的大小（宽度\高度）可以通过  `width`  和  `height`  指定。
-   图片是自闭合标签，你可以直接在开始标签结尾添加反斜线（`<img />`），而不用像其他标签那样额外添加一个结束标签。

在下面的例子中，我们使用了一张叫做 “nefertiti” 的 JPG 图片

```
<img
  src="images/nefertiti.jpg"
  alt="A smiling Labrador Retriever"
  width="480"
  height="320"
/>

```

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/f4be330b-3406-4c6a-911b-c1871e1165d6/concepts/07b685e8-61c1-434a-b756-daa923790caf#)

![一只微笑的拉布拉多犬](https://video.udacity-data.com/topher/2019/August/5d49f85a_nefertiti/nefertiti.png)

一只微笑的拉布拉多犬

### 链接

链接在 HTML 中很重要，因为 Web 的最初设计就是一些相互关联的信息网络文档。你通过点击一个链接从一个页面跳转到另一个页面。

HTML - “超文本标记语言”，意味着我们使用的链接类型是超文本链接，也称为超链接。

在 HTML 中，链接是用  `<a>`  标记的内联元素。然后，我们通过  `href`  属性来指定链接地址 (即，单击时跳转的地址)。

跳转地址有以下三种类型:

-   锚定目标，用来在同一页面内部跳转
-   相对地址，用来在同一个网站内部跳转
-   绝对地址，通常用来跳转到其他网站

你还可以使用除了  `a`  和  `href`  之外的其他属性:

-   使用  `rel`  属性指定当前文档和链接文档之间的关系
-   使用  `target`  属性指定打开链接的方式

在下面的例子中，我们将 URL 地址设置为了 Labrador Club 网站。为了防止它访问  `window.opener`  属性，确保在单独的进程中运行，我们指定了 rel 属性为  `noopener`。最后，我们希望链接在新窗口打开，而不是当前窗口，所以指定了 target 属性值为  `_blank`。

```
<a href="https://thelabradorclub.com" rel="noopener" target="_blank"
  >Join The Labrador Retriever Club</a>

```

### 注释

如果你在代码中编写了一些内容，但是并不会影响到浏览器的显示内容，你就是在编写注释。

浏览器会忽略掉注释，所以它只对编写代码的人有用。注释有助于其他人 (你同事、经理) 或者是你自己以后阅读代码时的代码理解。

注释以  `<!--`  开头，以  `-->`  结尾。

## 自闭合元素

一些 HTML 元素只有开始标签:

```
<!-- 换行符 -->
<br />
<!-- 图片 -->
<img src="https://dog.com/image.png" alt="Description" />
<!-- 文本输入框 -->
<input type="text" />

```

因为它们没有结束标签，内部不能包含任何内容，所以自闭合元素通常带有一些属性来为它们提供更多信息。

### 练习题

下面关于 HTML 属性的描述，哪个是正确的？

-   所有 HTML 元素都可以拥有属性，这些属性定义了元素的各种特性，比如  `img`  中的  `src`，`a`  元素中的  `href`。
    
-   只有部分元素拥有属性，并且使用 CSS 规则来定义元素的特性。
    

提交

## 知识扩展

更多关于 HTML 元素的知识，点击[这里](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)。

# 文档对象模型（Document Object Model, DOM）

了解 HTML 的层次结构是很重要的，因为子元素可以从其父元素那继承行为和样式。

Play Video

**备注:**  如果你想要像 Daniel 那样查看网站的 HTML ，你可以使用[谷歌开发者工具](https://developers.google.com/web/tools/chrome-devtools/)来查看网站代码。

现在，你已经了解了一些最常见的 HTML 元素，可以开始学习如何创建 HTML 文件了。HTML 文件需要文档类型声明才能正确显示文档。通过文档类型声明，可以使 Web 浏览器知道这是 HTML。声明看起来像这样：

`<!DOCTYPE html>`

这项声明是一条指令，并且必须是 HTML 文档中的第一行代码。它告诉浏览器你希望创建的文档类型，以及文档中的 HTML 版本。目前浏览器默认  `<!DOCTYPE html>`  中的 html 指的是 HTML5 版本，因为它是当前的标准。当然，以后可能会有新的标准来取代 HTML5。

为了保证你的文档能够被正确解析，请一定在 HTML 文档的开始处添加  `<!DOCTYPE html>`。

## Head 标签

目前，你应该已经完成了两项操作:

1.  通过  `<!DOCTYPE html>`  向浏览器声明你的文件类型为 HTML。
2.  添加  `<html>`  标签来包裹你的代码。

### 元数据

还记得  `<body>`  标签吗？`<head>`  标签也是 HTML 中的一部分，它通常会放置在  `<body>`  上面。

`<head>`  用于包含网页的元数据。元数据是一些关于网页的信息，但是不会显示在页面上。

与  `<body>`  中的正文内容不同，head 中的元数据更多是关于页面本身的信息。

### 标题

`<title>`  标签中的信息会作为标题显示在浏览器 tab 栏中。记住，`<title>`  标签总是放置在  `<head>`  标签里。

```
<!DOCTYPE html>
<html>
  <head>
    <title>My Coding Journal</title>
  </head>
</html>

```

以上代码告诉我们，浏览器会在顶部标题栏 (或者 tab 栏) 中显示 “My Coding Journal”。

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/f4be330b-3406-4c6a-911b-c1871e1165d6/concepts/08b569f1-4331-4d6a-b9e4-18a6829e8647#)

![titles 示例](https://video.udacity-data.com/topher/2019/August/5d49f8ba_title-tag/title-tag.png)

titles 示例

## Body 标签

```
<body></body>

```

有了 body 标签后，你就可以加入许多不同类型的内容进去，比如文本、图片、按钮等等。

## 层次结构

HTML 元素以家族树的方式组合在一起。比如，我们在  `<body>`  标签中放置了一个  `<p>`  标签。当一个元素被另一个元素包裹时，它就是这个元素的子元素，也就是说子元素被嵌套在父元素的内部。

```
<body>
  <p>This paragraph is a child of the body</p>
</body>

```

在上面的例子中，`<p>`  被嵌套在  `<body>`  的内部。`<p>`  就是  `<body>`  的子元素，而  `<body>`  则是父元素。你还可以看到，我们也添加了两个缩进空格来提高可读性。

由于可以有多个层级的嵌套，所以可以有孙元素、曾孙元素等等。元素和他的祖先元素以及后代元素之间的关系就是层次结构。

让我们用一些新标签来试试一个更复杂的例子:

```
<body>
  <div>
    <h1>Sibling to p，but also grandchild of body</h1>
    <p>Sibling to h1，but also grandchild of body</p>
  </div>
</body>

```

在这个例子中，`<body>`  是  `<div>`  的父元素，`<h1>`  和  `<p>`  都是  `<div>`  的子元素。由于  `<h1>`  和  `<p>`  在同一级，所以他们也叫做兄弟元素，并且都是  `<body>`  的孙元素。

再重复一次，了解 HTML 层次结构很重要，因为子元素可以从其父元素继承行为和样式，当你开始学习 CSS 时，会了解到更多有关网页层次结构的信息。

## 语义元素

语义元素可以帮助你组织页面的主要部分。它们通常用于包含其他 HTML 元素。

一个典型的网页可能包含以下部分:

-   `<header>`  作为页面的第一个元素，可以包含图标和标语
-   `<nav>`  是一个指向网页不同部分的列表
-   `<h1>`  用于表示网页的标题
-   `<article>`  是页面的主要部分，类似一篇博客文章
-   `<footer>`  是页面最后一个元素，通常位于页面底部

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/f4be330b-3406-4c6a-911b-c1871e1165d6/concepts/08b569f1-4331-4d6a-b9e4-18a6829e8647#)

![语义元素结构图例子](https://video.udacity-data.com/topher/2019/August/5d49f8f2_html-sectioning-elements/html-sectioning-elements.png)

语义元素结构图例子

# 表单

表单是日常生活的一部分。当我们在现实生活中使用物理表单时，我们会写下信息然后提交给某人进行处理。想一下你在生活中可能遇见的情况，比如填写工作信息，银行账户，或者一个完整的建议信息，它们都是表单的例子。

类似物理表单，HTML  `<form>`  元素也负责收集信息，然后发送到其他地方。在日常上网的时候，我们会接触到一些表单，甚至你都可能没有意识到这是表单。比如，你在一个文本框中输入内容，这个文本框很可能就是  `<form>`  的一部分。

在本课中，我们将会了解  `<form>`  的结构、语法以及组成元素。

通过 HTML 表单元素，我们可以收集网站访问者的输入信息。邮件列表，联系人表单，博客评论区域等，都是常见的例子，对于一些依赖表单盈利的公司来说，表单甚至是神圣的。

表单就好像是 “摇钱树”。在线电子商务通过它销售产品，SaaS 公司通过它收取客户的费用，非盈利组织通过它筹集资金。 许多公司也会通过表单的活跃程度来衡量成功度，比如 “销售团队从网站上获取了多少潜在客户？” “有多少人注册了我们的产品？” 等一系列问题。表单通常需要不断的测试和优化。

HTML 表单有多种类型：文本输入框，文本区域，单选按钮，复选框，下拉菜单和按钮等等。

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/f4be330b-3406-4c6a-911b-c1871e1165d6/concepts/40b67fe1-51d0-4788-8baf-682793921a20#)

![表单示例](https://video.udacity-data.com/topher/2019/August/5d49f95d_form-types/form-types.png)

表单示例

### 输入框类型，下拉框和文本区域输入框

文本框（text），复选框（checkbox）和单选按钮（radio button）类型由 “input type” 指定。

```
<!-- A text input -->
<input type="text" />
<!-- A checkbox -->
<input type="checkbox" />
<!-- A radio button -->
<input type="radio" />

```

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/f4be330b-3406-4c6a-911b-c1871e1165d6/concepts/40b67fe1-51d0-4788-8baf-682793921a20#)

![单选按钮示例](https://video.udacity-data.com/topher/2019/August/5d49f977_input-types/input-types.png)

单选按钮示例

另外，可以使用  `select`  创建下拉框

```
<label for="color-select">Choose a color:</label>

<select id="color-select">
  <option value="">--Please choose an option--</option>
  <option value="blue">Blue</option>
  <option value="red">Red</option>
  <option value="green">Green</option>
  <option value="yellow">Yellow</option>
  <option value="orange">Orange</option>
  <option value="pink">Pink</option>
</select>

```

----------

Choose a color:  --Please choose an option--  Blue  Red  Green  Yellow  Orange  Pink

----------

最后是文本区域  `textarea`  ，它创建了一个更自由的输入区域让用户输入信息。

```
<label for="learn">What do you hope to learn today?</label>

<textarea id="learn" name="learn" rows="5" cols="30">
I hope to learn about...
</textarea>

```

----------

What do you hope to learn today?

----------

### 更多关于表单的内容

以下链接提供了更多相关信息：[HTML 表单](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)、[select](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)、[textarea](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea).


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkwNTI2NjQ1M119
-->
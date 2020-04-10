# CSS 选择器

Play Video

### 标签选择器

在这个章节中，你会学习如何使用不同 CSS 视觉效果来装饰某个或某一组元素。

CSS 可以通过使用元素的标签名称来选中 HTML 元素。 标签名称就是被尖括号包括起来的字母。

举个例子，在 HTML 中，代表段落的标签是  `<p>`。 那么在 CSS 中对应选中  `<p>`  的语法就是：

```
p {
  color: red;
}

```

在上面的例子中，所有的段落标签都会被 CSS 选择器选中。例子中对应的选择器是  `p`。需要注意的是，虽然这里的CSS 选择器和对应的 HTML 元素匹配，但是它不需要用尖括号包裹。

然后，紧跟着选择器后面的内容是两个大括号。大括号内部所有的 CSS 属性都会应用到所选中的元素上。

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/25962c91-c1d5-47a4-9580-ac6ff3a151ed/concepts/c119e703-4ad0-4e8b-808d-5d9f77757d2d#)

![ CSS 选择器、属性、值的示例](https://video.udacity-data.com/topher/2019/August/5d4b3669_css-selector/css-selector.png)

CSS 选择器、属性、值的示例

### 类名选择器

在 CSS 中不一定只能通过标签来选中元素。HTML 元素除了标签名称之外，也可以拥有属性。一个常用的属性就是类名属性，我们也可以通过类名来选中一个元素。

比如，看看下面这个 HTML：

```
<p class="brand">Sole Shoe Company</p>

```

这个例子中的段落标签有一个类名属性。类名属性的值是 "brand"。如果我们想选中这个元素的话，我们可以使用下面的 CSS 选择器：

```
.brand {

}

```

通过类名选中 HTML 元素的话，我们需要在类名前面加一个英文句号 (`.`)。在这个例子中，元素的类名是 “brand”，所以对应的 CSS 选择器就是  `.brand`。

### id 选择器

有时候你可能想添加更具体的样式，这个时候你可以通过 id 属性来选中元素。你的 id 和类名可以是不同的值（而且，不一定要有类名）。比如，下面这个 HTML ：

```
<p id=”solo” class="brand">Sole Shoe Company</p>

```

你可以在一个元素上同时添加一个  `id`  属性和类名属性。 在 CSS 中的话，你需要在 id 前面添加一个井号  `#`  来表明它是一个 id ，类似你选中类名时添加的  `.`。 选中上面的元素并设置样式看起来可能是下面这样：

```
#solo {
  color: purple;
}

```

### 伪类

CSS 伪类是一些关键字，通常用于添加在一个选择器后面来指定一些特殊效果。比如  `:hover`，它的效果就是：当你把鼠标移动到一个按钮上时改变按钮颜色。

```
selector:pseudo-class {
  property: value;
}

```

如果你想知道更多关于伪类的知识，[点击这里查看](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)。

### 习题 1/2

下面哪个是 CSS 伪类的正确使用方式？

-   #myButton:hover { }
    
-   #myButton hover { }
    
-   #myButton { hover: }
    

提交

### 属性选择器

属性选择器是一种特殊的选择器，根据元素的属性和属性值进行匹配。

它的基本语法包含了一对方括号 (`[]`)，方括号里是一个属性名称，也可以包含一些额外条件，来根据属性值匹配。

属性选择器可以根据它们匹配值的方式划分为两种：

1.  精准匹配选择器
2.  模糊匹配选择器

这些属性选择器用来精准匹配一些属性值：

-   `[attr]`  这个选择器会选中所有带有 attr 属性的元素，不管它的值是什么。
-   `[attr=val]`  这个选择器会选择所有带有 attr 属性，且属性值为 val 的元素。
-   `[attr~=val]`  这个选择器会选中所有带有 attr 属性的元素，它的属性值可以有多个，但是必须包含了 val值（稍微有一些复杂，你可以点击这里([https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)查看）。](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)%E6%9F%A5%E7%9C%8B%EF%BC%89%E3%80%82)

### 习题 2/2

使用属性选择器，你会如何选择一个拥有  `alt`  属性的  `<img>`  元素 ？

-   `img[alt]`
    
-   `img=alt`
    
-   `img > alt`
    
-   `img.alt`
    

提交

### 多项选择器

如果我们想给所有的标题都添加一些同样的样式怎么办？ 我们不想增加多余的规则，因为维护成本很高，而且也不利于扩展。

```
h1 {
  font-family: "Helvetica", "Arial", sans-serif;
}

h2 {
  font-family: "Helvetica", "Arial", sans-serif;
}

h3 {
  font-family: "Helvetica", "Arial", sans-serif;
}

h4 {
  font-family: "Helvetica", "Arial", sans-serif;
}

h5 {
  font-family: "Helvetica", "Arial", sans-serif;
}

h6 {
  font-family: "Helvetica", "Arial", sans-serif;
}

```

以上对每一级标题都分别设置了同样的样式。其实，我们可以利用之前的规则选中多个 HTML 元素，并应用同一种样式，只需要用逗号把它们分割开就可以了。比如，在 styles.css 文件里添加下面的内容：

```
h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "Helvetica", "Arial", sans-serif;
}

```

这样，我们就给所有标题都设置了同样的字体样式。这样很方便，因为如果我们以后想改变它的话，只需要在这一个地方修改就行了。对于 web 开发者来说，复制和粘贴代码并不高效，多项选择器可以帮助我们提高效率。

# 引入 CSS

Play Video

### 内联方式

虽然 CSS 和 HTML 是不同的语言，但是我们可以在 HTML 中编写 CSS 代码。

你可以在 HTML 开始标签内部直接添加一个 style 属性来给它添加样式，你可以设置属性值为任何你想添加的 CSS 样式规则。

```
<p style="color: red;">I'm learning to code!</p>

```

这个例子中的代码展示了如何使用内联样式。这个段落标签的开始标签中有一个 style 属性。然后，我们在 style 属性中设置了  `color: red;`，这个属性会将我们段落文本颜色设置为红色。

你可能会对  `color: red;`  这段代码感到一些疑惑。现在先不用关心它的细节；以后的练习中你会学习到更多关于 CSS 的语法。现在，你只需知道内联 CSS 是一种最快最直接添加样式的方式。

如果你想继续添加更多的样式，可以继续在内联标签中添加，只不过不要忘记结尾的 (`;`) 符号。

```
<p style="color: red; font-size: 20px;">I'm learning to code!</p>

```

你也可以在 HTML 元素的 style 属性中粘贴一些 CSS 样式。在 dummy.html 中，我们有一个无效的链接，让我们通过 CSS 把它变成红色，来表明它是一个无效链接。

```
<p>
  Want to try crossing out an
  <a href="nowhere.html" style="color: #990000; text-decoration: line-through;">obsolete link</a>
  ? This is your chance!
</p>

```

和单独页面中的样式一样，我们使用的 CSS 语法都是一样的。 只不过这里它们作为属性值，所以需要把它们放置在一行中。而且，内联样式拥有最高的权重。这里我们定义的 color 和 text-decoration 属性会覆盖所有其他样式。 即使我们过后通过  `<style>`  元素定义了 text-decoration: none 也不会生效。

你应该避免使用内联样式，因为这样我们就不能通过外部样式表来改变它。 假设你想改变一些网站样式，你不能只改变全局的 styles.css 样式文件，你必须找到每个页面中的对应元素，然后改变元素里的内联样式，这样会很麻烦。

也就是说，如果你想给某个特殊 HTML 元素添加样式，大部分时候我们推荐使用 CSS 类名选择器，而不是使用内联样式。

### Style 标签

内联样式可以很快地给 HTML 添加样式，不过它有很多局限性。比如你想给  `<h1>`  元素添加样式，那么你必须手动给每个标签都添加样式。而且，你还必须考虑到未来添加的  `<h1>`  标签。

幸运的是，HTML 允许我们在元素内部单独编写 CSS 代码，比如  `<style>`  元素内。 你可以在  `<style>`  开始标签和结束标签之间编写 CSS 代码。 注意，为了使用  `<style>`  元素，你需要把它放置在你的  `<head>`  元素内部。

```
<head>
  <style></style>
</head>

```

在 head 标签中添加了  `<style>`  标签之后 ，你就可以开始编写 CSS 代码了。

```
<head>
  <style>
    p {
      color: red;
      font-size: 20px;
    }
  </style>
</head>

```

上面例子中的 CSS 代码会将所有的段落文本都设置成红色，字体大小为 20 像素。 可以看到，`<style>`  标签里的 CSS 代码和你在内联标签中编写的是一样的。 区别就是，使用前者，你需要指定你想要改变样式的元素。

### 外部样式表

如果 HTML 和 CSS 代码在不同的文件，你需要引入它。不然 HTML 文件并不会加载这些 CSS 代码，样式也不会生效。

你可以使用  `<link>`  元素来连接 HTML 和 CSS 文件。  `<link>`  元素必须放置在 HTML 文件中的 head 内。 它是一个自闭合标签，需要有下面 3 个属性：

-   `href`  — 和其他链接元素一样，这个属性用来指明你 CSS 文件的地址。
-   `type`  — 这个属性用来指明的引入的文件类型。 这里应该设置为 text/css。
-   `rel`  — 这个属性用来描述 HTML 文件和 CSS 文件的关系。

因为你在引入一个样式表，所以  `rel`  的值应该是 stylesheet。

一个用来连接 HTML 文件和 CSS 文件的 link 元素看起来大概是这样：

```
<link href="https://udacity.com/style.css" type="text/css" rel="stylesheet" />

```

使用 URL 指定样式表的路径是其中一种方式。

如果 CSS 文件和你的 HTML 文件在同一个文件夹下，你也可以通过一个相对路径来指定它的位置：

```
<link href="./style.css" type="text/css" rel="stylesheet" />

```

大多数情况下我们都会使用相对路径的方式。

```
<link rel="stylesheet" href="styles.css" />

```

实际上，在 HTML5 中，你不需要手动指明  `type="text/css"`。

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/25962c91-c1d5-47a4-9580-ac6ff3a151ed/concepts/9959d5bd-b1dc-4f37-83c9-4e2636d03bfa#)

![HTML 和 CSS 文件的关系](https://video.udacity-data.com/topher/2019/August/5d4b36a9_css-file-relationship/css-file-relationship.png)

HTML 和 CSS 文件的关系

# 权重

Play Video

因为一个元素可以被多个选择器选中，所以选择器之间会有一个优先级关系。 以下是它们依次从低到高的关系：

-   类型选择器 (e.g., h1) 和 伪类元素 (e.g.,  `::before`)
-   类名选择器 (e.g.,  `.example)`，属性选择器 (e.g.,  `[type="radio"]`) 和 伪类选择器 (e.g.,  `:hover`)
-   ID 选择器 (e.g.,  `#example`)

这些关系能帮助你弄清楚为什么你的一些样式没有生效。

除此之外，有一个特殊的情况就是在 CSS 属性后面使用了  `!important`  关键字，它会覆盖掉其他样式，而且有两个需要特别注意的地方：

在使用  `!important`  关键字之前，优先考虑使用其他权重的方式。 永远不要在全局的 CSS 样式中使用  `!important`  关键字。

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/25962c91-c1d5-47a4-9580-ac6ff3a151ed/concepts/bfdd28c9-1186-4e09-a8d5-c34e08c28b3a#)

![Specificity levels](https://video.udacity-data.com/topher/2019/August/5d4b3731_css-specificity1/css-specificity1.png)

权重从高到低

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/25962c91-c1d5-47a4-9580-ac6ff3a151ed/concepts/bfdd28c9-1186-4e09-a8d5-c34e08c28b3a#)

![Specificity explanation - example](https://video.udacity-data.com/topher/2019/August/5d4b3791_css-specificity2/css-specificity2.png)

权重示例

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/25962c91-c1d5-47a4-9580-ac6ff3a151ed/concepts/bfdd28c9-1186-4e09-a8d5-c34e08c28b3a#)

![Specificity explanation - example](https://video.udacity-data.com/topher/2019/August/5d4b37be_css-specificity3/css-specificity3.png)

权重示例

### 练习题

根据 CSS 中的权重关系，请问，链接会是什么颜色?

```
.link-text {
  color: red;
}

ul li a {
  color: green;
}

ul a {
  color: yellow;
}

a {
  color: blue;
}

```

```
<ul>
  <li><a class="link-text">the link</a></li>
  <li>a list item</li>
  <li>a list item</li>
</ul>

```

-   red
    
-   green
    
-   yellow
# 盒模型

Play Video

就像 CSS、HTML 和 JS 是构成 web 的基础元素一样，盒模型是 CSS 中的基础元素。

每个初学者都应该从基础开始学习。 在 CSS 中，盒模型就是基础。 在学习其他 CSS 概念之前，我们应该先熟悉一下它。

盒模型是 CSS 中的基础元素。

当浏览器渲染一个页面上的元素时，比如一段文本，或是一个图片，它都会按照 CSS 盒模型的规则，将元素渲染成一个个矩形盒子。

在深入理解它之前，你要记住，页面上的每个元素，实际上都是一个矩形的盒子。 你甚至可能在之前就已经听说过，因为它确实是每个开发者都必须熟悉的知识。

根据盒模型的概念，每个页面上的元素都是一个矩形盒子，拥有宽度、高度、内边距、边框和外边距等等。

现在，让我们来看看盒模型到底是怎么一回事。

### 内容区域

首先，是盒子本身的内容区域，它拥有一个宽度和高度。

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/25962c91-c1d5-47a4-9580-ac6ff3a151ed/concepts/40e40c66-c516-41fe-affb-af72cb969139#)

![内容区域盒子有一个宽度和高度。](https://video.udacity-data.com/topher/2019/August/5d4b384e_css-content/css-content.png)

内容区域盒子有一个宽度和高度。

### 内边距

接下来就是内边距 - 内边距就是元素内容区域和边框之间的部分。 注意内边距不包含在元素的宽度和高度中，但也是在元素的内部。

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/25962c91-c1d5-47a4-9580-ac6ff3a151ed/concepts/40e40c66-c516-41fe-affb-af72cb969139#)

![内边距在内容区域之外](https://video.udacity-data.com/topher/2019/August/5d4b38ee_css-padding/css-padding.png)

内边距在内容区域之外

### 边框

沿着我们盒模型的中心继续向外走，我们会遇到边框：围绕着元素内容区域和内边距的线。边框属性使用一种我们还没见过的新语法。 首先，我们需要定义边框线的宽度，然后是它的样式，最后再是它的颜色。

这里告诉浏览器在我们的标题周围画一条灰色的细线。 注意看边框是如何出现在内边距周围的，它们之间没有空隙。 如果你把浏览器窗口缩小到标题分为两行，边框和内边距依然会存在。

在标题四周都画上边框会让它显得有些古板，我们可以稍微限制一下它，和内边距一样，边框属性也可以有  `-top`,  `-bottom`,  `-left`, and  `-right`  变体，用来指明具体的边框线位置。

`border-bottom: 1px solid #5D6063;`

边框是很常见的设计元素，但是也可以用它帮助我们调试代码。如果你不确定一个元素是如何渲染的，你可以添加一个边框  `border: 1px solid red;`  然后你就可以看见的盒子的内边距，外边距，所有相关的布局属性等等，通过一行代码就可以完成。 在你找到错误的地方之后，再删除它就好了，很简单。

如果你之前使用过 word 或者是 excel 表格，你应该很熟悉边框。 在 CSS 中，你可以给任何元素添加边框。

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/25962c91-c1d5-47a4-9580-ac6ff3a151ed/concepts/40e40c66-c516-41fe-affb-af72cb969139#)

![边框是内边距和外边距之间的线](https://video.udacity-data.com/topher/2019/August/5d4b3919_css-border/css-border.png)

边框是内边距和外边距之间的线

### 外边距

最后要说的是外边距，外边距环绕在盒子周围，也就是一个盒子和另一个盒子之间的空隙。

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/25962c91-c1d5-47a4-9580-ac6ff3a151ed/concepts/40e40c66-c516-41fe-affb-af72cb969139#)

![外边距环绕在盒子外面，用来把其他盒子区分开。](https://video.udacity-data.com/topher/2019/August/5d4b3937_css-margin/css-margin.png)

外边距环绕在盒子外面，用来把其他盒子区分开。

### 练习题

内边距和外边距的区别是什么?

-   外边距在元素周围添加了一条线，内边距在元素内部填充一些额外空间。
    
-   外边距在元素内部填充空间，内边距在元素周围填充空间。
    
-   外边距在元素周围填充空间，内边距在元素内部填充空间。

# 显示和定位: Inline & Block

Play Video

外部显示方式之间的最大区别就是，一个元素是否会占据整行的页面空间（记住元素在 DOM 中是按照层次结构组织的）；还是它只会占据内容所需要的空间，剩余的元素可以紧接着和它摆放在同一行。

这里我们有两个 HTML 标签，它们都有一个 box 的类名：

```
<div class=”box”>Box 1</div>
<div class=”box”>Box 2</div>

```

如果我们在 CSS 代码中设置  `box`  的 display 属性为  `block`，那么每个元素会占据单独的一行，一个接一个的上下排列。但是，如果我们设置  `display`  属性为  `inline-block`，那么它们会在同一行依次排列，以下是对应的 CSS 代码：

```
.box{
  display: inline-block;
}

```

`inline`  通常用于高亮一大段本文中的一些特殊文字，`span`  元素就是一个例子。 display 属性设置为  `inline`  的元素没有宽度和高度，只会占据它内部文本或者 （`.innerHTML`  属性）的空间。所以在上面的  `box`  例子中，每个矩形盒子会显示在同一行，并且宽度和内部的文本宽度一致。

# 显示和定位: Z-index

当 HTML 元素重叠时，它们的顺序取决于在 z 轴上的位置（谁应该显示在最上面）。z 轴的位置可以用 CSS 中的 z-index 属性来决定。 z-index 数值越大的元素会覆盖其他数值较小的元素。

元素重叠的原因有很多，比如对元素使用了绝对定位，或者某一个元素的外边距是负数。元素重叠时，我们需要通过一种方式来指定谁显示在最上面。如果你没有显式地指定  `z-index`的话，那么 DOM 中的最后一个元素会显示在最上层，依次类推。

来看一个例子，假如我们有两个矩形，它们都采用了绝对定位(absolute)。代码如下：

```
<style>
.box {
  width: 200px;
   height: 200px;
  position: absolute;
}

#one {
  background: red;
  top: 100px;
  left: 150px;
}

#two {
  background: yellow;
  top: 80px;
  left: 100px;
}
</style>

<html>
  <div id=”one” class =”box”> Box One </div>
  <div id=”two” class =”box”> Box Two </div>
</html>

```

默认情况下，id 为  `two`  的元素会显示在上面，因为在代码里，它在  `one`  元素后面。 如果我们想让第一个元素显示在上面的话，可以使用  `z-index`，通过赋给每个元素  `z-index`  数值，从而让数值大的元素显示在上面。 我们修改一下 CSS 代码：

```
#one {
  background: red;
  top: 100px;
  left: 150px;
  z-index:1;
}

#two {
  background: yellow;
  top: 80px;
  left: 100px;
  z-index: -1;
}

```

注意，元素  `one`  的  `z-index`  设置为了  `1`，元素  `two`的  `z-index`  设置为了  `-1`。如果你有更多元素的话，你也可以把数字范围设置大一些，规则都是一样的。一个拥有  `z-index`  为 100 的元素会显示在  `z-index`  为 99 的元素上方，以此类推。


# 绝对单位 VS 相对单位

许多 CSS 属性都需要一个度量单位。有许多常见单位可供使用，包括  `px`（像素）和  `em`（发音类似单词 m）。前者就是单纯的像素值，而后者则会根据当前元素的字体大小决定。

CSS 中的度量单位有 2 种，绝对单位和相对单位。

**绝对单位**

-   `px`
-   `in`
-   `mm`
-   `cm`

绝对单位的意思是它和你的项目或浏览器无关。  `px`  是最常用的绝对度量单位，许多页面上的字体大小都在 12px 到 30px 之间。一个  `16px`  大小的字体在任意大小屏幕上的显示情况都是一样的。 不过，如果你想基于一些动态值来设置 CSS 属性值，比如根据浏览器的宽度来设置，你也可以使用一些相对的度量单位。

**相对单位**

-   `%`  - 根据一些元素的百分比设置，比如屏幕宽度。
-   `em`  - 根据当前的字体大小来设置 - 比如字体大小是 12px，那么 2em 就是 24px。
-   `vw`  - 根据当前视觉窗口来计算，1vw 等于百分之一的视觉窗口宽度。
-   `vh`  - 和上面的 vw 类似，不过是根据视觉窗口高度计算。

当你在想要根据基础字体大小定义尺寸时，em 单位很有用。 比如，你可以设置  `body`  的字体大小为  `16px`，然后根据它来设置其他元素的字体大小，就像这样：

```
body {
 font-size: 16px;
}

#one {
  font-size: 1.5em
}

#two {
  font-size: 0.5em
}

```

在这个例子中，元素  `one`  的字体会比 16px 大，而元素  `two`  的字体则会比 16px 小。

# 排版样式

Play Video

### 文本对齐

text-align 属性定义了 HTML 元素中文本的对齐方式。

```
p {
  text-align: left;
}

```

其他可以使用的值有 right (右对齐)， center (居中) 或 justify (两端对齐)。

### 习题 1/2

请问，下面的 CSS 样式会应用到哪些元素上？

```
.has-text-centered {
  text-align: center;
}

```

-   `<div class="has-text-centered">`
    
-   `<a href="#" class="has-text-centered">`
    
-   `<button class="has-txt-centered">`
    
-   `<p class="has-text-centered has-text-primary is-size-5">`
    
-   `<div class="has-text-centered-justified">`
    

提交

### 文字下划线

text-decoration 属性可以用来设置一段文本是否拥有下划线。 通过把 text-decoration 设置为 none 可以去除链接上的默认下划线，我们会在后面在深入讨论链接。

```
a {
  text-decoration: none;
}

```

### 删除文本

另一个常用的 text-decoration 属性是 line-through，用来实现文本删除效果。不过通常你应该使用 HTML 而不是 CSS 来完成这些效果。如果要实现文本删除的效果，更好的方式是使用  `<ins>`  和  `<del>`  元素，而不是在 CSS 中使用 line-through。

### 行高

和文本对齐一样，本文之间的间距也很关键。在这里，我们来看看 3 个和它相关的 CSS 属性：

-   `margin-top`  (以及  `padding-top`)
-   `margin-bottom`  (以及  `padding-bottom`)
-   `line-height`

你应该已经很熟悉前面两个属性了，它们可以用来定义段落之间的距离。 第三个  `line-height`  （行高）属性可以用来定义段落内部文本行与行之间的垂直距离。 在传统排版样式中，行高也叫做行距，因为打印机会使用更少的铅条，来增加文本之间的间距。

### 习题 2/2

请问，行高的用处是什么？

-   用于控制段落元素之间的距离
    
-   用于控制字体高度的大小
    
-   用于控制字体之间的宽度
    
-   用于控制两行内容之间的距离

# 字体

### 字体类型

`font-family`  也是一个内置的 CSS 属性，你可以用它来定义任何元素的字体。 它可以接受多个值，因为并不一定所有的用户都安装有相同的字体。

当你在 Web 上使用字体时，你需要考虑你的用户能使用哪些字体。 每个系统都有一些自带的字体，比如 Window，OSX，Linux 等等，你可以直接使用它们。了解更详细的 Web 安全字体，可以点击[这里](https://web.mit.edu/jmorzins/www/fonts.html)。

字体使用方式很简单。 当你使用 font-family 属性时，你只需要指定你想要使用的字体就好了。

浏览器会从左到右，依次根据你提供的字体来检测是否可用。如果第一个字体不可用，它就会继续查找下一个，以此类推。

指定多个字体的目的就是因为并不是所有操作系统都支持同一种字体，所以设置多个类似的字体，可以确保用户在不同的操作系统下拥有一致的体验。

### 字体粗细 & 风格

在 CSS 中，字体粗细用 100 到 900 之间的数值表示。 不过，也有一些对应的更易于阅读的术语可以使用。 “Black” 通常表示 900，“bold” 是 700，“regular” 表示 400，等等。 不是每一种字体都会为每一种粗细设置一个值。比如 Roboto 字体就缺少 “extra light” (200)，“semi bold”（600），以及 “extra bold” （800）。

注意，每种样式的粗细都是单独重新设计的。 在高质量字体中，简体字体不是单纯的把字体压扁，粗体字体也不是单纯的把字体加粗一些，它们都是纯手工单独设计过的，确保文字显得更自然。

许多衬线字体中的斜体和罗马字体尤为明显，比如 Century Schoolbook FS 中的小写字母 “a” 的斜体形状就完全不同。

#### 强调 & 加粗

为了强调一个单词，我们可以使用  `<em>`  标签（通常是变为斜体）。

```
<p>
  We <em>have</em> to buy the latest version of the pet hair remover vacuum, the
  floor is covered with fur!
</p>

```

这是它的显示结果：

We  _have_  to buy the latest version of the pet hair remover vacuum, the floor is covered with fur!

对于一些重要的单词，我们可以使用  `<strong>`  标签来包裹它。 默认情况下，`<strong>`  包裹的文本会显示为粗体，但这只是浏览器的默认行为。不要使用  `<strong>`  标签来加粗字体，而是用它来体现某个文本的重要程度高一些。

```
<p>
  My dog is the most <strong>important</strong> creature in my life right now.
</p>

```

## 外部字体

可以有多种方法来使用外部托管的字体。 其中一个常用的例子是  [Google 字体](https://fonts.google.com/)，它提供了大量免费的字体让你使用，你可以访问下面的 Google 字体网站，选择你喜欢的字体，它会提供给你对应字体的代码，你可以把这些代码放置在你的  `head`  区域内部：

```
<head>
  <link href="https://fonts.googleapis.com/css?family=Montserrat&display=swap" rel="stylesheet">
</head>

```

然后在 CSS 代码中，你可以这样设置元素的字体属性：

```
.box{
  font-family: 'Montserrat', sans-serif;
}

```

在这个例子中我选择的 Google 字体是 “Montserrat”。

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/25962c91-c1d5-47a4-9580-ac6ff3a151ed/concepts/a225edc8-7556-4ac0-a17f-d5082e443e3c#)

![外部托管字体和本地字体的例子对比。](https://video.udacity-data.com/topher/2019/August/5d4b3995_css-fonts/css-fonts.png)

外部托管字体和本地字体的例子对比。

# 颜色

CSS 中的颜色可以通过以下方法指定：

1.  十六进制颜色
2.  RGB 颜色
3.  预定义/跨浏览器的颜色名称
4.  RGBA 颜色
5.  HSL 颜色
6.  HSLA 颜色

前三种最常用，我们来看看。

### 十六进制颜色

十六进制颜色用  `#RRGGBB`  的方式指定，其中 RR（红色）、GG（绿色）和 BB（蓝色）分别是用十六进制整数指定的不同组成部分。所有的数值必须在 00 到 FF 之间。

比如，`#0000ff`  值会被渲染为蓝色，因为它的蓝色部分设置为了最高值（ff），而其他部分全都是 00。

#### 例子

定义不同的十六进制颜色：

```
#p1 {
  background-color: #ff0000;
}

#p2 {
  background-color: #00ff00;
}

#p3 {
  background-color: #0000ff;
}

```

## RGB 颜色

RGB 颜色值使用  `rgb()`  函数指定，语法如下：

`rgb(red, green, blue)`

每个参数（红色，绿色，蓝色）定义了不同颜色的浓度，可以指定为 0 到 255 的整数，或是通过百分比指定（从 0% 到 100%）。

例如  `rgb(0,0,255)`  的值会呈现为蓝色，因为蓝色部分的参数设置为了最高值，而其他参数都是 0。`rgb(0%,0%,100%)`的效果和  `rgb(0,0,255)`一样，都是蓝色。

#### 例子

定义不同的 RGB 颜色：

```
#p1 {
  background-color: rgb(255, 0, 0);
}

#p2 {
  background-color: rgb(0, 255, 0);
}

#p3 {
  background-color: rgb(0, 0, 255);
}

```

### 预定义/跨浏览器的颜色名称

HTML 和 CSS 颜色规范中预定义了 140 个颜色名称。

你可以点击查看颜色名称的[列表](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value)。

### 习题 1/2

请问，下面哪项不是正确的 CSS 颜色值？

-   `color: #FFF;`
    
-   `color: rgb(255, 255, 255);`
    
-   `color: #FFFFFF;`
    
-   `color: FFFFFF;`
    

提交

### 习题 2/2

请问，下面哪些颜色值代表了蓝色?

-   `color: #ff0000;`
    
-   `color: blue;`
    
-   `color: rgb(0, 0, 255);`
    
-   `color: #ffff00;`
    
-   `color: #00f;`
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExMjA5NzE5MjZdfQ==
-->
# Grid vs Flexbox

Play Video

Flexbox 是关于内容的流向，而 Grid 则更关注内容的结构。 Grid 很擅长搭建页面结构，而 flexbox 则可以用于控制 grid 中的单个区域。

# Grid vs Flexbox 例子

将 flexbox 和 grid 结合使用的一个比较好的方式是使用 grid 来搭建页面布局，然后使用 flexbox 来控制其中的元素流向。 让我们来看一个例子吧！

Play Video

你可以通过设置元素的  `display`  属性为  `grid`  来使用 CSS grid。

[](https://classroom.udacity.com/nanodegrees/nd0011-cn/parts/51c03f53-9630-4cde-a76e-bb32c9761a81/modules/a280da9f-d026-43e4-a06c-279d7bff7faa/lessons/eb6fbc90-f3d1-4ff7-99ad-ce245cf1ff92/concepts/b347a6a0-81c3-460d-8600-51af2b03c7d6#)

![flexbox 可以和 Grid 结合使用](https://video.udacity-data.com/topher/2019/August/5d4dbc95_gridvflex/gridvflex.png)

flexbox 可以和 Grid 结合使用

### 练习题

在 web 项目中我们只能选择使用 CSS grid 或 flexbox 其中之一吗？

-   是的，CSS Grid 取代了 Flexbox
    
-   不是，CSS Grid 和 Flexbox 可以很好的结合使用
    

提交

### 总结

CSS Grid vs. Flexbox

-   Grid 是一种二维布局方式，而 Flexbox 是一维的。
-   Grid 重点关注布局, 而 Flexbox 重点关注内容的流向。
-   Flexbox 适用于应用的组件，而 Grid 适用于应用本身的布局。

CSS Gird 并不是 Flexbox 的替代者，它们都有各自擅长的地方，专业的开发者应该灵活结合使用它们，来创造出所需的页面布局。

总体来说，CSS Grid 擅长搭建布局结构，而 Flexbox 则擅长处理元素的流向。

### 更多资源

更多关于 CSS Grid 的信息，可以点击下面链接查看:

-   [Beginner’s Guide to choosing between CSS Grid and Flexbox](https://medium.com/youstart-labs/beginners-guide-to-choose-between-css-grid-and-flexbox-783005dd2412)
-   [The Ultimate CSS Battle: Grid vs. Flexbox](https://hackernoon.com/the-ultimate-css-battle-grid-vs-flexbox-d40da0449faf)
-   [Does CSS Grid Replace Flexbox?](https://css-tricks.com/css-grid-replace-flexbox/)
# 行 & 列

Play Video

通过 display 属性将元素设置为 grid 之后，你就可以使用下列 CSS 属性来控制其中的行与列了：

-   `grid-template-columns`
-   `grid-template-rows`

你也可以通过在容器元素上使用  `grid-gap`  属性来控制行与列之间的间隙。

# 行 & 列 实战

你可以通过  `grid-template-columns`  属性来设置网格中列的样式，也就是你想将容器垂直划分为多少块区域，每个值用来显式指定列的宽度，列的数量则由其中的实际数值个数隐式决定：

```
grid-template-columns: 60px 60px;

```

这里会创建两列，每列 60 像素宽，如果你在网格中有两个项目，但未明确设置其位置，则第一个项目将放置在第一列中，第二个项目放置在第二列中。  `grid-template-rows`  也遵循相同的逻辑，所以：

```
grid-template-columns: 60px 60px;
grid-template-rows: 160px 60px;

```

将会创建两行和两列布局。

让我们在实际例子中看看吧！

Play Video

可以通过使用  `grid-template-columns`  和  `grid-template-rows`  来控制网格中的布局样式。

### 练习题

下面哪一个选项是正确的 CSS grid 语法?

-   `grid-template-rows: 160px 60px;`
    
-   `grid--rows: 160px 60px;`
    
-   `template-rows: 160px 60px;`
    
-   `rows: 100px 100px;`
    

提交

Setting Up

Starting Workspace VM.

**Please wait**_Loading…_

练习：在  `index.html`  文件中，将  `container`  变成一个  `grid`  网格容器，同时在网格容器中通过行和列来改变当前的默认布局。

CSS Gird 由行与列组成，这些行与列通过  `grid-template-columns`  和  `grid-template-rows`  来指定，并决定它们所占据的空间。

### 更多资源

你可以尝试一下这个很酷的项目来加深理解：[grid visualizer and generator](https://cssgrid-generator.netlify.com/)。

# Grid 区域

Play Video

`grid-area`  用于指定项目所要占据的行和列中的某一具体区域，就像下面这样：

```
.item{
  grid-area: 1/2/3/3
}

```

`grid-area`  是下列属性的简写：  `grid-row-start`,  `grid-column-start`,  `grid-row-end`  以及  `grid-column-end`。所以，以上代码的意思是元素会占据第一行到第三行，第二列到第三列的空间。

# 使用 Grid Areas

`grid-area`  通过指定元素的开始行、开始列、结束行与结束列，来决定元素所占据的位置，看起来就像这样：

```
  #one {
    /* row start/column start/ row end/ column end */
    grid-area: 1/2/3/3;
  }

```

在这个例子中，`one`  元素会从第一行开始，到第三行结束，从第二列开始，到第三列结束，如果没有第三行，则会在第二行末尾结束。

让我们来看看实际的情况吧！

Play Video

`grid-area`  是下列属性的简写：  `grid-row-start`,  `grid-column-start`,  `grid-row-end`  和  `grid-column-end`。它定义了一个元素在网格中所占据的空间。

Setting Up

Downloading files to your Workspace.

**Please wait**_Loading…_

练习：在工作区中，通过  `grid-area`  属性来改变  `one`  元素的位置和尺寸：

-   使元素拉伸撑满整个 grid，但是只对第一行生效。
-   使元素拉伸撑满整行，但是只对第一列生效。
-   自由发挥 - 创建你自己的元素区域……或者要不试着添加第二个元素然后设置  `grid-area`  中的位置？

### Grid 区域 总结

`grid-template-areas`  用于设置元素在网格中所占据的行列空间，看起来是下面这样：

```
  .container {
      display:grid;
      grid-template-columns: 300px 300px 300px;
      grid-template-rows: 250px 600px;
      grid-template-areas:
      "hd hd hd hd hd hd hd hd"
      "sd sd sd main main main main main"
      "ft ft ft ft ft ft ft ft";
  }

```

你可以根据上面定义的名称来决定把什么元素放入对应的位置:

```
.header {
  grid-area: hd;
}

```

在上面的例子中，带有  `header`  类名的元素会占据网格中第一行的整行空间，因为我们设置了  `grid-area`  为  `hd`, 同时我们也在 grid 容器中设置了对应的  `grid-template-areas`  属性。

# 使用 Grid Areas II

Setting Up

Starting Workspace VM.

**Please wait**_Loading…_

练习：在  `index.html`  中，为  `header`,  `footer`,  `sidebar`,  `content`  等内容分配网格区域。 可以使用  `grid-template-areas`！

### 更多资源

CSS grid 非常灵活，用处很大。你可以阅读这篇文章，了解更多详情：[Complete Guide to Grid, from CSS-Tricks here](https://css-tricks.com/snippets/css/complete-guide-grid/)。

# Grid 进阶

Play Video

CSS Gird 包含了一些高级特性来创建大型和复杂的网格，比如:

-   `fr`  单位
-   用于重复的  `repeat()`  函数
-   用于设置大小范围的  `minmax()`  函数

让我们在实战中试试这些特性吧!

Play Video

# Grid 进阶：练习区

下面的 HTML 工作区中包含了上一节中的练习答案。这里没有明确的练习要求，你可以自由发挥，尽可能地尝试你的 Grid 高级技能吧！

Setting Up

Starting Workspace VM.

**Please wait**_Loading…_

### Grid 进阶 总结

`fr`  单位用来表示 grid 容器中可用空间的一等份。

`repeat()`  函数可以在大型网格中用来快速创建区域，例如：

```
grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr 1fr;

```

可以通过使用 repeat 函数简化成这样：

```
grid-template-columns: repeat(7, 1fr);

```

`grid-auto-rows`  属性可以用来定义隐式创建的行所占的空间，例如：

```
grid-auto-rows: minmax(100px, auto);

```

这样可以创建一组行，其下限为 100 像素高，上限根据元素内容动态决定。

### 更多资源

了解更多关于 CSS Grid 的内容，请阅读这篇文章：[How Items Flow Into a CSS Grid](https://gedd.ski/post/grid-item-placement/)。
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5Njc0NTIxMTVdfQ==
-->
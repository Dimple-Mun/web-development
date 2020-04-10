# 弹性盒子简介

Play Video

Flexbox：弹性盒子。  
我们通过将一个元素的 display 设置为 flex 来使用弹性盒子。该元素内的元素会自动成为弹性子元素，然后就可以在 CSS 代码中使用弹性盒子语法了

# 弹性盒子示例

让我们来快速看一些弹性盒子能做的事

Let's take a quick look at some of the key things that Flexbox can do.

Play Video

通过将元素的  `display`  属性设置为  `flex`，它内部的所有元素都会成为弹性子元素，然后你就可以按照行或列的方式对它们进行居中、对齐等操作，从而搭建你想要的自定义布局。

### 练习题

如何在你的代码中使用弹性盒子 ？

-   通过将父元素的  `display`  属性设置为  `flex`。
    
-   通过将父容器内部子元素的  `display`  属性设置为  `flex`.
    
-   直接开始使用  `align-items`  和  `justify-content`  等属性就可以了.
    

提交

Setting Up

Starting Workspace VM.

**Please wait**_Loading…_

练习：在  `index.html`  文件中，设置  `container`  容器的 display 属性为  `flex`。你应该会看到盒子发生变化。

Flex 是一组 CSS 规则，用于在父容器中自动扩展多列和多行。 这是一个特殊的 CSS 属性，你需要一个主容器+容器内部的一些子元素。有些 CSS 弹性盒子属性用在主容器上，而另一些则会用在内部的子元素上。

为了使用弹性盒子，你需要设置父容器的  `display`  属性为  `flex`，像这样：

```
.container{
  display:flex;
}

```

### 更多资源

想了解更多关于弹性盒子的信息, 点击[这里](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)

# 弹性盒子的轴与方向

Play Video

弹性盒子模型有两个轴：主轴和副轴。主轴通过 flex-direction 属性来定义，一共有下面四种情况：

-   `row`
-   `row-reverse`
-   `column`
-   `column-reverse`

前两种情况会将设置主轴为水平方向，即元素排成行（`inline`）。后两种情况会将主轴设置为垂直方向，即元素排成列（`block`）。  `block`  和  `inline`  就是我们之前在 CSS 里学过的内联和块状方式。

轴的方向属性决定了内容的流向——水平行方向或是垂直列方向，进而决定了如何在弹性容器中居中和对齐元素。

# 轴和方向示例

如上一页面所述，将元素的 display 属性设置为 flex 之后，下一件事就是设置容器内元素的排列方式，按行还是按列。 我们可以使用  `flex-direction`  属性来设置。

Play Video

你可以通过  `flex-direction`  属性来控制弹性盒子里的元素布局（行或列），像这样：

```
.container{
  display:flex;
  flex-direction: row
}

```

### 练习题

以下哪些陈述是正确的？（多选题）

-   如果设置  `flex-direction`  为  `row`  或  `row-reverse`，主轴方向会是水平方向。
    
-   如果设置  `flex-direction`  为  `column`  或  `column-reverse`，主轴方向会是垂直方向。
    
-   如果主轴是水平的，副轴就是垂直的。
    
-   两个轴决定了弹性盒子中内容的流向，同时也决定了  `align-items`  和  `justify-content`  属性的最终效果。
    

提交

Setting Up

Starting Workspace VM.

**Please wait**_Loading…_

练习：在工作区添加必要的 CSS ，让父容器变成一个弹性盒子，同时其中的子元素排列成一列显示。

轴和方向是弹性盒子的重要概念，不管从概念上还是技术上，理解起来可能都有一点棘手。建议你先在笔记本上画出类似的盒子模型和轴，有助于理解。

### 更多资源

想了解更多关于弹性盒子轴与方向的知识，请点击[这里](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox#The_two_axes_of_flexbox)。

# 使用弹性盒子排序元素

Play Video

可以通过 3 种方式来设置网格中的元素顺序：

1.  通过直接改变 HTML 代码中的元素顺序
2.  通过使用  `row-reverse`  或  `column-reverse`  可以翻转弹性盒子里行和列的元素顺序
3.  通过使用  `order`  属性来改变每个子元素的排列顺序
# 元素排序示例

`flex-direction: row`  会从左到右依次排列元素，而  `flex-direction: row-reverse`  会翻转元素顺序，从右往左依次排列元素。也就是说，我们可以通过在 row 和 columns 属性上添加  `-reverse`  后缀来翻转元素排列顺序。

Play Video

### 练习题

下面哪种是错误的弹性盒子排序方式？

-   修改 HTML 代码中的元素顺序。
    
-   通过在  `row`  和  `column`  属性后面添加  `-reverse`  后缀来翻转元素的顺序。
    
-   将元素名称改为按数字排序的方式。
    
-   在每个子元素上使用  `order`  属性。
    

提交

Setting Up

Starting Workspace VM.

**Please wait**_Loading…_

练习：`index.html`  中的弹性子元素目前成一列显示，且从上到下依次排列，重写代码使元素变成一行显示，且顺序从右往左。 你可以有多个方式来完成它！

### 更多资源

了解更多关于弹性盒子中元素排序的知识，请点击[这里](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#Ordering_flex_items)。

# 在弹性盒子中对齐和居中元素

Play Video

你可以使用  `align-items`  在副轴上对齐元素，它有下列值可以使用：

-   stretch
-   flex-start
-   flex-end
-   center

你可以使用  `justify-content`  在主轴上居中元素，它有下列值可以使用：

-   flex-start
-   flex-end
-   center
-   space-around
-   space-between
-   space-evenly
# 对齐和居中示例

使用弹性盒子的主要目的，就是控制元素布局，包括对齐、居中和分布。接下来，我们会重点学习弹性盒子的两个强大属性（`align-items`  和  `justify-content`），学习如何使用它们来创建优雅布局。

Play Video

### 练习题

请勾选正确的陈述。

-   align-items 属性会决定元素在副轴上的对齐方式。
    
-   Justify-content 属性会决定元素在副轴上的对齐方式。
    
-   align-items 属性会决定元素在主轴上的对齐方式。
    

提交

Setting Up

Starting Workspace VM.

**Please wait**_Loading…_

练习：在  `index.html`  文件中，更新 style 来居中和对齐 box 中的元素。

### 更多资源

了解更多关于这节内容的知识，请点击[这里](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox#Alignment_justification_and_distribution_of_free_space_between_items)。

实用建议：参阅文档可以使你变得更聪明，更加爱上编写代码！
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTYxMjcxMzAxMV19
-->
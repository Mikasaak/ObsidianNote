tching Title#28ik](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Containing_block)
# 布局和包含块
一个元素的尺寸和位置经常受其**包含块**（containing block）的影响。大多数情况下，包含块就是这个元素最近的祖先[块元素](https://developer.mozilla.org/zh-CN/docs/Glossary/Block-level_content)的[内容区域](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model#%E5%86%85%E5%AE%B9%E5%8C%BA%E5%9F%9F)，但也不是总是这样。在本文中，我们来过一遍确定包含块的所有因素。

当一个客户端代理（比如说浏览器）展示一个文档的时候，对于每一个元素，它都产生了一个盒子。每一个盒子都被划分为四个区域：

1. 内容区
2. 内边距区
3. 边框区
4. 外边距区

![Diagram of the box model](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Containing_block/box-model.png)

许多开发者认为一个元素的包含块就是他的父元素的内容区，但这不一定正确。接下来让我们来看看，确定元素包含块的因素都有哪些。

## [包含块的影响](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Containing_block#%E5%8C%85%E5%90%AB%E5%9D%97%E7%9A%84%E5%BD%B1%E5%93%8D)

在学习如何确定元素包含块之前，先了解一下它的重要性。

元素的尺寸及位置，常常会受它的包含块所影响。对于一些属性，例如 [`width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/width), [`height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/height), [`padding`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding), [`margin`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin)，绝对定位元素的偏移值（比如 [`position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/position) 被设置为 `absolute` 或 `fixed`），当我们对其赋予百分比值时，这些值的计算值，就是通过元素的包含块计算得来。

## [确定包含块](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Containing_block#%E7%A1%AE%E5%AE%9A%E5%8C%85%E5%90%AB%E5%9D%97)

确定一个元素的包含块的过程完全依赖于这个元素的 [`position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/position) 属性：

1. 如果 position 属性为 **`static`**、**`relative`** **或 `sticky`**，包含块可能由它的最近的祖先**块元素**（比如说 inline-block, block 或 list-item 元素）的内容区的边缘组成，也可能会建立格式化上下文 (比如说 a table container, flex container, grid container, 或者是 the block container 自身)。
2. 如果 position 属性为 **`absolute`** ，包含块就是由它的最近的 position 的值不是 `static` （也就是值为`fixed`, `absolute`, `relative` 或 `sticky`）的祖先元素的内边距区的边缘组成。
3. 如果 position 属性是 **`fixed`**，在连续媒体的情况下 (continuous media) 包含块是 [viewport](https://developer.mozilla.org/zh-CN/docs/Glossary/Viewport) ,在分页媒体 (paged media) 下的情况下包含块是分页区域 (page area)。
4. 如果 position 属性是 **`absolute`** 或 **`fixed`**，包含块也可能是由满足以下条件的最近父级元素的内边距区的边缘组成的：
    1. [`transform`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transform) 或 [`perspective`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/perspective) 的值不是 `none`
    2. [`will-change`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/will-change) 的值是 `transform` 或 `perspective`
    3. [`filter`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/filter) 的值不是 `none` 或 `will-change` 的值是 `filter`（只在 Firefox 下生效）。
    4. [`contain`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/contain) 的值是 `layout`、`paint`、`strict` 或 `content`（例如：`contain: paint;`）
    5. [`backdrop-filter`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/backdrop-filter) 的值不是 `none`（例如：`backdrop-filter: blur(10px);`）

**备注：** 根元素（[`<html>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/html)）所在的包含块是一个被称为**初始包含块**的矩形。它具有视口（对于连续媒体）或页面区域（对于分页媒体）的尺寸。

**备注：** `perspective` 和 `filter` 属性对形成包含块的作用存在浏览器之间的不一致性。

## [根据包含块计算百分值](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Containing_block#%E6%A0%B9%E6%8D%AE%E5%8C%85%E5%90%AB%E5%9D%97%E8%AE%A1%E7%AE%97%E7%99%BE%E5%88%86%E5%80%BC)

如上所述，当某些属性被赋予一个百分比值时，它的计算值取决于这个元素的包含块。以这种方式工作的属性包括**盒模型属性**和**偏移属性**：

1. [`height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/height)、[`top`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/top) 及 [`bottom`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/bottom) 属性根据包含块的 `height` 计算百分比值。
2. [`width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/width)、[`left`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/left)、[`right`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/right)、[`padding`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding) 和 [`margin`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin) 属性根据包含块的 `width` 计算百分比值。

**备注：** 一个**块容器**（比如 inline-block、block 或 list-item 元素）要么只包含参与行级格式化上下文的行级盒子，要么只包含参与块级格式化上下文的块级盒子。只有包含块级或行级盒子的元素才是块容器。
# 面试官：说说你对 CSS 盒模型的理解

[前端小蜜蜂来也](https://juejin.cn/user/2867156542299816/posts)

2023-04-112,051阅读3分钟

专栏： 
你想知道的前端都在这里

#### 前言

CSS 盒模型是 CSS 基础的重点难点，因此常被面试官们拿来考察候选人对前端基础的掌握程度，这篇文章将对 CSS 盒模型知识点进行全面的梳理。

我们先看个例子：下面的 div 元素的总宽度是多少呢？

js

复制代码

`<!DOCTYPE html> <html> <head> <meta charset="utf-8">      <title>CSS 盒模型(https://github.com/webharry/fe-interview)</title> <style> div {     background-color: lightgrey;     width: 200px;     border: 10px solid yellow;     padding: 10px;     margin: 20px; } </style> </head> <body>     <div>这里是盒子内的实际内容。有 10px 内间距，20px 外间距、10px 黄色边框。</div> </body> </html>`

要回答这个问题，我们首先得弄明白 CSS 盒模型。

### 什么是 CSS 盒模型？

每个HTML元素都由一个矩形框（盒子）组成，称为盒模型。CSS 盒模型定义了一个 HTML 元素的尺寸和边距。

#### 盒模型的各个部分

CSS 中组成一个盒子需要：

- **Content box**: 这个区域是用来显示内容，大小可以通过设置 `width` 和 `height`。
- **Padding box**: 包围在内容区域外部的空白区域；大小通过 `padding` 相关属性设置。
- **Border box**: 边框盒包裹内容和内边距。大小通过 `border` 相关属性设置。
- **Margin box**: 这是最外面的区域，是盒子和其他元素之间的空白区域。大小通过 `margin` 相关属性设置。

如图所示：

![CSS 盒模型各个部分](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/451dae42b3fd4a878f4c0d3811d26fb9~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

## CSS 有两种盒模型：标准盒模型和IE盒模型。

- 标准盒模型：元素的宽度和高度只包括内容（content），不包括内边距（padding）、边框（border）和外边距（margin）。
- IE盒模型：元素的宽度和高度包括内容（content）、内边距（padding）和边框（border），但不包括外边距（margin）。

### 两种盒模型的区别是什么？

这两种盒模型的区别在于它们如何计算元素的宽度和高度，以及如何处理元素的内边距、边框和外边距。

- 在标准盒模型中，元素的宽度和高度只包括内容，因此设置宽度和高度时需要考虑内边距、边框和外边距对它们的影响。
    
    - 如图：
    
    ![标准盒模型](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f061d3d8d9664d44825685d76350c456~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)
- 而在IE盒模型中，元素的宽度和高度包括内边距和边框，因此设置宽度和高度时不需要考虑内边距和边框对它们的影响。
    
    - 如图：
    
    ![IE盒模型](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/53bea950f7824186b0c8af9af07054e2~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

**重要:**  当您指定一个 CSS 元素的宽度（width）和高度（height）属性时，你只是设置内容区域（content）的宽度和高度。

### 两种盒模型间如何转换？

可以通过设置 CSS 的 box-sizing 属性来指定使用哪种盒模型。默认情况下，box-sizing 属性的值为 content-box，即使用标准盒模型。可以将其设置为 border-box，即使用IE盒模型。

### 写在最后

现在，我们再来看文章开头的例子，答案显而易见。因为在默认情况下，box-sizing 属性的值为 content-box，即使用标准盒模型。所以例子中的 div 元素总宽度是 200+10x2+10x2=240px。

如果这篇文章对你有帮助，请不要吝啬你手中的赞👍！你的鼓励将是我不断分享的动力！😄
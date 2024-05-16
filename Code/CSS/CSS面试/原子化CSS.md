# 初探原子化CSS

[爱吃葡萄的葡萄子](https://juejin.cn/user/88377513740253/posts)

2022-05-022,507阅读2分钟

## 原子化Css了解

### 什么是原子化css

- **原子化 CSS(Atomic CSS): 原子化 CSS 是一种 CSS 的架构方式，它倾向于小巧且用途单一的 class，并且会以视觉效果进行命名；有些人可能会称其为函数式 CSS，或者 CSS 实用工具。本质上，可以将原子化的 CSS 框架理解为这类 CSS 的统称**

css

复制代码

`.m-0 {     margin: 0; } .text-red {     color: red; } /* ... */`

- 优缺点
    - 优点
        
        1. **减少了** **css** **体积，提高了css复用**
        2. **减少起名的复杂度**
    - 缺点
        
        1. **增加了记忆成本**
        2. **增加了** **html** **结构的复杂性**

### 相关框架

1. ## [Tailwind CSS](https://link.juejin.cn/?target=https%3A%2F%2Fwww.tailwindcss.cn%2F "https://www.tailwindcss.cn/")
    
    - Tailwind CSS 是一个功能类优先的 CSS 框架，它集成了诸如 `flex`, `pt-4`, `text-center` 和 `rotate-90` 这样的的类，它们能直接在脚本标记语言中组合起来，构建出任何设计享受原子化 CSS 带来的快速开发体验
    - Tailwind CSS 作为 Vitesse 的默认 UI 框架，虽然 Vite 较 Webpack 等工具相比，在加载速度上有了大幅提升，但由于 Tailwind 生成了数 MB 的 CSS，使得加载与更新 CSS 成为了整个 Vite 应用的性能瓶颈
2. ## [Windi CSS](https://link.juejin.cn/?target=https%3A%2F%2Fcn.windicss.org%2F "https://cn.windicss.org/")
    
    - Windi CSS 是从零开始编写的 Tailwind CSS 的替代方案。它的零依赖，也不要求用户安装 PostCSS 和 Autoprefixer。更为重要的是，它支持 **按需生成**。Windi CSS 不会一次生成所有的 CSS，而是只会生成你在代码中实际使用到的原子化 CSS。这与 Vite 按需使用的理念不谋而合，也因此，我为它编写了 [一个 Vite 插件](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Fwindicss%2Fvite-plugin-windicss "https://github.com/windicss/vite-plugin-windicss")。不出所料，从一个简单的测试上可以看到它比 Tailwind 要快了 20~100 倍。
3. ## [UnoCSS](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Funocss%2Funocss "https://github.com/unocss/unocss")
    
    - 具有高性能且极具灵活性的即时原子化 CSS 引擎
    - UnoCSS 是一个**引擎**，而非一款**框架**，因为它**并未提供核心工具类**，所有功能可以通过预设和内联配置提供
    - UnoCSS 仍处于实验阶段，但由于其精简的设计，生成的结果已经非常可靠了；需要注意的一点是，API 还没有最终定案
    - 它并非被设计成 Windi CSS 或 Tailwind 的替代品（考虑等待 Windi CSS v4），不建议将现有项目完全迁移到 UnoCSS。可以在新的项目中试用它，或者将它作为你现有 CSS 框架的补充（例如，禁用默认预设，只使用纯 CSS 图标的预设，或者自定义你的规则）
4. ## [Fower](https://link.juejin.cn/?target=https%3A%2F%2Ffower.vercel.app%2Fzh-cn%2F "https://fower.vercel.app/zh-cn/")
    
    - Fower 是一个高效开发 UI 的样式工具库，目标是让写 CSS 不再痛苦。Fower 的核心特点是原子化(Atomic/utility-first)、类型安全(Type Safe)、CSS in JS，它非常注重开发体验，让用户快速且开心的开发界面
    - 不依赖任何框架，可与React，Vue，React native，小程序等框架一起使用


# 使用原子化 CSS 的一些感悟

2023-12-17

预计 12 分钟

目前在公司的项目中已经大量地使用了原子化 CSS 一段时间了，包括我们的小程序项目和 Web 项目，所以简单总结一下一些实践后的总结与感悟

什么是原子化 CSS 呢？可以看看 [Tailwind CSS](https://tailwindcss.com/) 或者 [UnoCSS](https://unocss.dev/) 的简介。简单来说，原来比较常见的做法是多个 CSS 属性组合成一个类名来赋予样式，而原子化 CSS 一个类只做一件事情（比如 `text-black` 就是 `color: black`），然后通过组合原子化类来赋予元素样式

## 优点

我认为原子化 CSS 带来的优点解决了很多原来开发过程的痛点

### 快速还原设计稿

还原设计的时候比较迅速，特别是设计团队收敛了 Design Token 的情况下，在你熟悉了设计系统的情况下，你甚至可能不需去审查元素的具体样式就能直接把设计稿还原了

如果你做自己的个人项目将没有专门的设计时候，像 Tailwind CSS 也提供了合理的预设，可以限制你随意写 CSS，编写出的页面也能符合一定规范并且相对美观

### 不再有命名烦恼

原本要给 `class` 起名，有些有语意的元素还好，如果你只是想给某个元素一个右间距，那到底是直接写个行内样式呢，还是给这个元素一个 `class`，然后起个名字，这种情况下名字叫什么常常会让人烦恼

### 体积

1. 目前像 Tailwind CSS 或者 UnoCSS，样式文件的生成都是按需生成的，不会包含没有用到的样式
2. 当项目增大到一定量级的时候，即使新增很多模块，样式大小也不怎么会变化了，因为一个项目中，原子化的样式数量也是有限的，新的模块可以复用大部分已有的原子化 CSS
3. 在小程序上，特别是业务比较重/功能比较多的小程序上，由于小程序单包体积有 2MB 的限制，你需要极致地去保证体积足够小，原子化 CSS 带来的好处会更加明显，因为体积问题直接影响了小程序是否能够正常发布

### 重构

使用原子化 CSS 可以非常自信的去去掉某个样式而不会引起其他部分出现问题

另外因为样式是和标记绑定的，删除标记的时候会顺带删除对应的样式

原来传统的方式做这些事情都是比较困难的，比如：

1. 即使全局搜不到某个类名，你可能都不敢删某个类，因为没准这个类是在代码中通过字符串拼接生成的
2. 你可能不敢删除一个后代选择器，因为你不确定当前元素是否会有匹配这个后代选择器的元素，除非你仔细阅读一下代码

## 缺点

我认为原子化 CSS 的缺点大部分都是属于可接受范围内的

### 类名长

Markup（HTML） 里的类名会很长，看起来可能会不方便，也没那么美观

### Debug 时去代码里找元素困难

这也是类名长所带来的问题，比如原来我去命名一个 `class` 的时候，取的这个名字在模块纬度甚至项目纬度重名是非常少的，遇到样式问题，全局一搜很快就能搜到

但是用了原子化 CSS，找代码可能会比较困难，如果将整个类复制出来搜索，也不一定能够搜到，因为可能元素的类名一部分是静态的，一部分是通过其他方式动态赋予的

### 优先级

这一点算是原子化 CSS 比较大的一个缺点了

比如我们在用 CSS 的时候，可能会写这样的代码，一般来说，一个元素会有一个基础样式，然后在不同状态，会有一些样式的覆写：

```
<template>  <div :class="['item', isActive && 'active']"></div></template><style>/** 基础 **/.item {  background: #f3f4f6;  color: #ef4444;  box-shadow: 0 1px 2px 0 rgb(0 0 0 / 0.05);}/** 不同的状态不同样式 **/.active {  color: #3b82f6;  box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);}</style>
```

但如果用原子化 CSS，这样可能就会有问题：

```
<template>  <div :class="['bg-gray-100 text-red shadow-sm', isActive && 'text-blue shadow-lg']" /></template>
```

这样的写法是比较符合「直觉」的，但你会发现即使 `isActive` 为 `true`，可能字体颜色还是红色

你需要像下面这样写，这里别扭的一点是，你需要把变与不变的抽离开来，保证表示相同属性的原子化类不重叠，但如果状态多了，管理起来就比较不方便，可能需要进一步引入一些代码组织方式让代码写起来更加优雅一些

```
<template>  <div :class="['bg-gray-100', isActive ? 'text-blue shadow-lg' : 'text-red shadow-sm']" /></template>
```

比如像社区就有 [tailwind-merge](https://www.npmjs.com/package/tailwind-merge) 这样的库去解决这个问题

## 感悟

总的来说，在业务项目中，我认为原子化 CSS 带来的优点多于缺点

在写这篇文章的时候，Meta 也已经正式开源了他的 CSS 框架，StyleX，他有一个章节，[Thinking in StyleX](https://stylexjs.com/docs/learn/thinking-in-stylex/)，也值得读一下，很多 StyleX 解决的问题，原子化 CSS 也解决了，当然，StyleX 也声称解决了很多原子 CSS 问题，比如优先级问题

结合着使用原子化 CSS 的体验，以及看了 StyleX 文档之后，说一说一些感想吧

现在很多编程语言都是非常强大的，像 CSS 这种 DSL 也非常强大，其中有很多我们压根听都没听过的功能。实现一个同样的功能，可能会有多种方法去供你选择，比如给 `.wrapper` 的直接子元素加一个 `8px` 的 `margin-bottom`

你可以这样写：

```
.wrapper > * {  margin-bottom: 8px;}
```

你也可以给每个子元素一个 `.item` 类，然后这样写：

```
.item {  margin-bottom: 8px;}
```

但在大型工程上，我们要去限制这种灵活性，我们可以通过规范去制定一个可以使用最小化的可使用集，这样带来的维护性是大大提升的，将来做整体的代码更改、代码分析也会容易很多

拿我实际遇到的问题来说，想要给一个没有指定 CSS 规范的项目进行样式方面的 codemod 是非常困难的，比如我曾想要把项目自动化地改为原子化 CSS 来优化包体积，最终无疾而终，因为项目中包含了各种后代选择、子代选择、子代选择中的元素包含元素选择器等等。极端一点举个例子，如果一开始，项目 CSS 规范约定不准有后代选择器，只能用类选择器定义样式，做这种 codemod 就可行了

我想到一个经典例子，Ruby 和 Python，虽然我都不怎么用过，但我听说 Ruby 是提供不同的方法做同一件事，Python 是有一种，最好只有一种方法来做一件事情，在编程语言上，这是一种设计哲学，不谈场景，无谓好坏，但在大型工程上，目前我更偏向的就是最好只有一种方法来做一件事情

JavaScript 有一本书《JavaScript 语言精粹》，里面说到很多不建议使用的 JavaScript 的语言特性，即使我们只使用 JavaScript 的一个「子集」，照样能做到「全集」所能做的事情

在关于样式的问题上，我也是这种看法，最近比较新的框架，Tailwind CSS、StyleX 也都是有着这样设计思路

约束，反而可以带来更多的可能性
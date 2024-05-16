---
description: 
pubDate:
tags: 
title: 未命名
date_created: 2024-05-16日 星期四 , 10:11:07 上午
date_modified: 2024-05-16日 星期四 , 10:11:15 上午
---
以下为整理的webpack面试题，如有不足之处，还请大家多多指正。

> **一、webpack的构建流程**
> 
> ![](https://img-blog.csdnimg.cn/f435cdbce99c4d6d809e8a7a44fa4c47.png)

> **二、对webpack的理解**
> 
>         webpack是一个打包模块化js的工具，在webpack里一切文件皆模块，通过loader转换文件，通过plugin注入钩子，最后输出由多个模块组合成的文件，webpack专注构建模块化项目。        
> 
>         webPack可以看做是模块的打包机器：它做的事情是，分析你的项目结构，找到js模块以及其它的一些浏览器不能直接运行的拓展语言，例如：Scss，TS等，并将其打包为合适的格式以供浏览器使用。

> **三、如何提高webpack的构建速度？**
> 
> ![](https://img-blog.csdnimg.cn/7086d56f3c634137a909370cbe118cce.png)

> **四、如何利用webpack优化前端性能？**
> 
> ![](https://img-blog.csdnimg.cn/d5f0f7f1c22f420c97dfa167384eef7c.png)

> **五、代码分割的本质是什么？**
> 
>         代码分割的本质就是在源代码直接上线和达成唯一脚本main.bundle.js这两种极端方案之间的一种更适合实际场景的中间状态。  
>         源码直接上线：虽然过程可控，但是http请求多，性能开销大。  
>         打包成唯一脚本：服务器压力小，但是页面空白期长，用户体验不好。

> **六、Webpack的基本功能有哪些？**
> 
> |   |   |
> |---|---|
> |**名称**|**内容**|
> |代码转换|TypeScript编译成JavaScript、SCSS编译成CSS等。|
> |文件优化|压缩JavaScript、csS、html代码，压缩合并图片等。|
> |代码分割|提取多个页面的公共代码、提取首屏不需要执行部分的代码让其异步加载。|
> |模块合并|在采用模块化的项目有很多模块和文件，需要构建功能把模块分类合并成一个文件。|
> |自动刷新|监听本地源代码的变化，自动构建，刷新浏览器。|
> |代码校验|在代码被提交到仓库前需要检测代码是否符合规范，以及单元测试是否通过。|
> |自动发布|更新完代码后，自动构建出线上发布代码并传输给发布系统。|

> **七、文件指纹是什么？**
> 
>         文件指纹是打包之后的文件后缀名。
> 
>         chunkhash：和webpack打包的chunk有关，不同的entry会生出不同的chunkhash。
> 
>                 js后缀名：filename:'[name][chunkhash:8].js',
> 
>         contenthash：根据文件内容来定义hash，文件内容不变，则其不变。
> 
>                 css后缀名：filename:'[name][contenthash:8].css',
> 
>         hash：和整个项目构建有关，只要项目文件有修改，整个构建的hash值就会修改。
> 
>                 img后缀名：name:'[name][hash:8].[ext]',

> **八、source map是什么？**
> 
>         将编译，打包，压缩后的代码映射回源码的过程，打包压缩后的代码不具有良好的可读性，想要调试源码就需要soucre map。
> 
>         **线上环境：避免在生产中使用inline-和eval-，因为他们会增加bundle体积大小，并降低整体性能。**
> 
>         1、hidden-source-map：借助第三方错误监控平台Sentry使用。
> 
>         2、nosources-source-map：只会显示具体行数以及查看源代码的错误栈。安全性比source map高。
> 
>         3、source map通过nginx设置将.map文件只对白名单开放（公司内网）。

> **九、说一下loader**
> 
>         loader 用于对模块的源代码进行转换。本质上是一个函数，在函数中对接收到的内容进行转化，返回转化后的结果。webpack只认识js，json，loader就成了翻译官。
> 
> **常用lodaer**
> 
> |   |   |
> |---|---|
> |file-loader|把⽂件输出到⼀个⽂件夹中，在代码中通过相对 URL 去引⽤输出的⽂件。|
> |url-loader|和 file-loader 类似，但是能在⽂件很⼩的情况下以 base64 的⽅式把⽂件内容注⼊到代码中去。|
> |source-map-loader|加载额外的 Source Map ⽂件，以⽅便断点调试。|
> |image-loader|加载并且压缩图⽚⽂件。|
> |babel-loader|将ES6转化为ES5。|
> |css-loader|加载 CSS，⽀持模块化、压缩、⽂件导⼊等特性。|
> |style-loader|把 CSS 代码注⼊到 JavaScript 中，通过 DOM 操作去加载 CSS。|
> |eslint-loader|通过 ESLint 检查 JavaScript 代码。|
> |less-loader|可以打包处理.less相关的文件。|
> |sass-loader|可以打包处理.scss相关的文件。|

> **十、如何保证各个loader按照预想方式工作？**  
>     可以使用enforce强制执行loader的作用顺序，pre代表在所有正常loader之前执行，post是所有之后执行。

> **十一、说一下plugins**
> 
>         webpack 插件是一个具有 apply 属性的 JavaScript 对象。apply 属性会被 webpack compiler 调用，并且 compiler 对象可在整个编译生命周期访问。
> 
>         由于插件可以携带参数/选项，必须在 webpack 配置中，向 plugins 属性传入 new 实例。

> **十二、描述一下编写loader或plugin的思路**  
>         loader像一个“翻译官”，把读到的源文件内容转义成新的文件内容，并且每个loader通过链式操作，把源文件一步步翻译成想要的样子。  
>         编写loader要遵循单一原则，每个loader只做一种“转义”工作，每个loader拿到的是源文件内容（source），可以通过返回值的方式将处理后的内容输出，也可以调用this.callback()方法，将内容返回给webpack。还可以通过this.async()生成一个callback函数，再用它将处理后的内容输出去。此外webpack还为开发者准备了开发loader的工具函数集——loader-utils。  
>         plugin编写比较灵活。webpack在运行的生命周期中会广播出许多事件，plugin可以监听这些事件，在合适的时机通过webpack提供的API改变输出结果。

>  **十三、bundle、chunk、module分别是什么？**  
>         bundle：是由webpack打包出来的文件  
>         chunk：代码块,一个 Chunk 由多个模块组合而成,用于代码合并与分割，这些模块是从入口模块通过依赖分析得来的。  
>         module：模块,在 Webpack 里一切皆模块,一个模块对应着一个文件。Webpack 会从配置的 Entry 开始递归找出所有依赖的模块。

>  **十四、文件监听原理是什么？**
> 
>         在发现源码发生变化时，自动重新构建出新的输出文件。  
>         **原理**  
>         轮询判断文件的最后编辑时间是否变化，如果某个文件发生了变化，并不会立刻告诉监听者，而是先缓存起来，等aggregateTimeout后再执行。  
>         **方式**  
>         启动 webpack 命令时，带上 --watch 参数。  
>         在配置 webpack.config.js 中设置 watch:true。  
>         **缺点**  
>         每次需要手动刷新浏览器。
> 
> ```javascript
> module.export = {     // 默认false,也就是不开启     watch: true,     // 只有开启监听模式时，watchOptions才有意义     watchOptions: {         // 默认为空，不监听的文件或者文件夹，支持正则匹配         ignored: /node_modules/,         // 监听到变化发生后会等300ms再去执行，默认300ms         aggregateTimeout:300,         // 判断文件是否发生变化是通过不停询问系统指定文件有没有变化实现的，默认每秒问1000次         poll:1000     } }
> ```

> **十五、模块打包原理是什么？**  
>         webpack 实际上为每个模块创造了一个可以导出和导入的环境，本质上并没有修改 代码的执行逻辑，代码执行顺序与模块加载顺序也完全一致。

> **十六、什么是webpack热更新原理？**
> 
>         webpack的热更新又称热替换（Hot Module Replacement），缩写为HMR。 这个机制可以做到不用刷新浏览器而将新变更的模块替换掉旧的模块。  
>         HMR的核心就是客户端从服务端拉去更新后的文件，准确的说是 chunk diff (chunk 需要更新的部分)，实际上 WDS 与浏览器之间维护了一个Websocket，当本地资源发生变化时，WDS 会向浏览器推送更新，并带上构建时的 hash，让客户端与上一次资源进行对比。客户端对比出差异后会向 WDS 发起Ajax请求来获取更改内容(文件列表、hash)，这样客户端就可以再借助这些信息继续向 WDS 发起jsonp请求获取该chunk的增量更新。 

> **十七、如何对bundle体积进行监控和分析？**  
>         VSCode中有一个插件Import Cost可以帮助我们对引入模块的大小进行实时监测，还可以使用webpack-bundle-analyzer生成bundle的模块组成图，显示所占体积。  
>         bundlesize工具包可以进行自动化资源体积监控。 

> **十八、Bable原理是什么？**
> 
>         大多数JavaScript Parser遵循estree规范，Babel 最初基于acorn项目(轻量级现代 JavaScript 解析器) Babel大概分为三大部分：  
>         **转换**  
>         访问 AST 的节点进行变换操作生产新的 AST。
> 
>                 词法分析：将代码(字符串)分割为token流，即语法单元成的数组。  
>                 语法分析：分析token流(上面生成的数组)并生成 AST。          
>         **生成**  
>         以新的 AST 为基础生成代码。
> 
>                 Taro就是利用 babel 完成的小程序语法转换。  
>         **解析**  
>         将代码转换成 AST。
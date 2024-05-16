---
description: 
pubDate:
tags: 
title: vue样式穿透的几种方式
date_created: 2024-05-13日 星期一 , 07:41:58 晚上
date_modified: 2024-05-13日 星期一 , 07:43:12 晚上
---
# vue样式穿透的几种方式

# `scoped`属性

我们在vue组件写样式一般是在`<style>`标签里面，但是我们在这里的样式默认是全局样式，如果其它组件的class名取重复了则会导致样式污染。

所以vue支持在`<style>`标签添加`scoped`属性，这样当前组件的样式只会在当前样式生效，其它组件不会影响到。

例子如下：

```html
<div class="page">
  <span class="content">hello world</span>
</div>
<style lang="scss" scoped>
.page {
  .content {
    color: aquamarine;
    font-size: 20px;
  }
}
</style>

```

最终在浏览器渲染出来，div和span上都带有特殊属性

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/d9de26dba4ae4b0b95ad23466ff5a8eb~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

然后css的样式最终也会带上这些属性，根据这些属性找到元素。

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7224f79ecc734b289c35824f83782b64~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

这样子避免样式全局污染。

如果你的引入了第三方库，如果你想修改第三方库的样式，直接通过dom查找，修改样式是没有效果的。

比如我在项目引入了饿了么的组件库`elementUI`。


```html
<el-card class="box-card">
  <span class="content">hello world</span>
</el-card>

```
![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/96d9c3f64fff4dac8781d97553395b0b~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

如果我们想把padding改小一点,下面这样写是没有效果的。

```html
<style lang="scss" scoped>
.box-card {
  .el-card__body {
    padding: 10px;
  }
}
</style>

```

只看到默认的padding。我们写的样式没有渲染出来。

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/19d350342f844a2487a6c4a9f45663f5~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

此时需要样式穿透，需要用到深度选择器`/deep/`。
```html
<style lang="scss" scoped>
.box-card {
  /deep/.el-card__body {
    padding: 10px;
  }
}
</style>

```

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/b397a5a84f264fa8a7d092a1ecab6e23~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

可以看到生效了。

# 样式穿透

vue都是通过深度选择器来样式穿透的。除了上面的讲`/deep/`，我熟知的还有`::v-deep`，`>>>`，`:deep()`。

那它们有何区别？

如果你使用的是`css`，没有使用css预处理器，则可以使用`>>>`，`/deep/`，`::v-deep`。

如果你使用的是`less`或者`node-sass`，那么可以使用`/deep/`，`::v-deep`都可以生效。

如果你使用的是`dart-sass`，那么就不能使用`/deep/`，而是使用`::v-deep`才会生效。

但是如果你是使用`vue2.7`以上版本以及包括`vue3`，`::v-deep`也会生效，但是会有警告⚠️

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f5c3083dbad14bf69f6c281c973ea413~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

警告说的很清楚，`::v-deep`已经废弃，应该使用`:deep()`

# 总结

总结一下：

- `css`可以使用`>>>`，`/deep/`，`::v-deep`
- `less`和`node-sass`可以使用`/deep/`，`::v-deep`
- `dart-sass`可以使用`::v-deep`
- `vue2.7`以上版本以及包括`vue3`，应该使用`:deep()`
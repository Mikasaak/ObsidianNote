---
description: 
pubDate:
tags: 
title: vue2响应式的缺点
date_created: 2024-05-2日 星期四 , 11:19:25 晚上
date_modified: 2024-05-2日 星期四 , 11:20:22 晚上
---
# vue2响应式的缺点

[不学习就代表退步](https://juejin.cn/user/1324239346216349/posts)

2022-05-164,918阅读1分钟

专栏： 

什么都有一点的vue专栏

响应式：数据改变-->视图跟着变

对象新增的属性没有响应式 数组的部分操作没有响应式

   push()，
   pop()，
   shift()，
   unshift()，
   splice()，
   sort()，
   reverse()

**以上7中API会修改原数组(vue2的内部重写了这7个API)**

其他的操作都不会有响应式

### 实际简单操作一波


```vue
<template>
  <div>
<span v-for="(item,index) in arr " :key="index">{{item}}</span>
<hr>
<button @click="arr[0]=100">点击把第一个元素变成100</button>
  </div>
</template>

<script>
export default {
data() {
    return {
        arr:[1,2,3]
    }
},


}
</script>

<style>
span{
    margin: 10px;
    background-color: orange;
    padding: 10px;
    border-radius: 5px;
} button{
    background-color: orange;
    font-size: 20px;
    border: 0;
    cursor:pointer;

}
</style>

```


![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6636e35152434649870f0f5a9b83a66c~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

你们会发现vue里面的数据其实已经改成100了,但是页面并没有渲染出来.

现在我们换一种,换成splice来操作

```vue
<template>
  <div>
<span v-for="(item,index) in arr " :key="index">{{item}}</span>
<hr>
<button @click="arr.splice(0,1,100)">点击把第一个元素变成100</button>
  </div>
</template>

<script>
export default {
data() {
    return {
        arr:[1,2,3]
    }
},


}
</script>

<style>
span{
    margin: 10px;
    background-color: orange;
    padding: 10px;
    border-radius: 5px;
} button{
    background-color: orange;
    font-size: 20px;
    border: 0;
    cursor:pointer;

}
</style>

```

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/149d6de281fd41ee8f3dc99f2f8db7eb~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)

数据修改的同时,dom也成功渲染
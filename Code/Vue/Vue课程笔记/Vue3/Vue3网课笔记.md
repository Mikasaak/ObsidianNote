---
description: 
pubDate:
tags: 
title: Vue3网课笔记
date_created: 2024-03-31日 星期日 , 04:58:07 下午
date_modified: 2024-04-23日 星期二 , 04:27:27 下午
---
官方文档地址：[Vue.js - 渐进式 JavaScript 框架 | Vue.js (vuejs.org)](https://cn.vuejs.org/)


### 1.Vue3项目结构

![[attachments/Untitled 84.png|Untitled 84.png]]

  

![[attachments/Untitled 1 7.png|Untitled 1 7.png]]

  

  

### 生命周期

![[attachments/Untitled 2 8.png|Untitled 2 8.png]]

#### 官方文档
生命周期钩子

每个 Vue 组件实例在创建时都需要经历一系列的初始化步骤，比如设置好数据侦听，编译模板，挂载实例到 DOM，以及在数据改变时更新 DOM。在此过程中，它也会运行被称为生命周期钩子的函数，让开发者有机会在特定阶段运行自己的代码。

注册周期钩子

举例来说，`onMounted` 钩子可以用来在组件完成初始渲染并创建 DOM 节点后运行代码：


```vue
	<script setup>
	import { onMounted } from 'vue'
	
	onMounted(() => {
	  console.log(`the component is now mounted.`)
	})
	</script>
```

还有其他一些钩子，会在实例生命周期的不同阶段被调用，最常用的是 [`onMounted`](https://cn.vuejs.org/api/composition-api-lifecycle.html#onmounted)、[`onUpdated`](https://cn.vuejs.org/api/composition-api-lifecycle.html#onupdated) 和 [`onUnmounted`](https://cn.vuejs.org/api/composition-api-lifecycle.html#onunmounted)。所有生命周期钩子的完整参考及其用法请参考 [API 索引](https://cn.vuejs.org/api/composition-api-lifecycle.html)。

当调用 `onMounted` 时，Vue 会自动将回调函数注册到当前正被初始化的组件实例上。这意味着这些钩子应当在组件初始化时被**同步**注册。例如，请不要这样做：



```js
setTimeout(() => {
  onMounted(() => {
    // 异步注册时当前组件实例已丢失
    // 这将不会正常工作
  })
}, 100)
```

注意这并不意味着对 `onMounted` 的调用必须放在 `setup()` 或 `<script setup>` 内的词法上下文中。`onMounted()` 也可以在一个外部函数中调用，只要调用栈是同步的，且最终起源自 `setup()` 就可以。

生命周期图示

下面是实例生命周期的图表。你现在并不需要完全理解图中的所有内容，但以后它将是一个有用的参考。

![[Pasted image 20240423162548.png|650]]

有关所有生命周期钩子及其各自用例的详细信息，请参考[生命周期钩子 API 索引](https://cn.vuejs.org/api/composition-api-lifecycle.html)。




### 2.setup

  

![[attachments/Untitled 3 8.png|Untitled 3 8.png]]

  

![[attachments/Untitled 4 8.png|Untitled 4 8.png]]

### 3.reactive() 和 ref()


> [!note]  关于    [[ref和reactive]]
> 在响应式对象中读取ref数据可以无需添加*.value*
> 例如：
> ```js
> const obj = reactive({
> 	a:  1,
> 	b:  2,
> 	c:  ref(8)
> })
> console.log(obj.c)//无需  .value
> ```
> 



![[Pasted image 20240402100641.png]]
  

![[attachments/Untitled 5 7.png|Untitled 5 7.png]]

  

![[attachments/Untitled 6 7.png|Untitled 6 7.png]]

  

![[attachments/Untitled 7 7.png|Untitled 7 7.png]]

### 4.watch

  

![[attachments/Untitled 8 7.png|Untitled 8 7.png]]

  

![[attachments/Untitled 9 7.png|Untitled 9 7.png]]

  

![[attachments/Untitled 10 7.png|Untitled 10 7.png]]

  

![[attachments/Untitled 11 6.png|Untitled 11 6.png]]

  

![[attachments/Untitled 12 6.png|Untitled 12 6.png]]


### watchEffect

![[Pasted image 20240402102202.png]]


### 5.ref获取DOM和vue组件

  

![[attachments/Untitled 13 6.png|Untitled 13 6.png]]

![[attachments/Untitled 14 6.png|Untitled 14 6.png]]

![[attachments/Untitled 15 6.png|Untitled 15 6.png]]

  

### 6.computed

  

  

![[attachments/Untitled 16 6.png|Untitled 16 6.png]]

[![](https://www.notion.so)](https://www.notion.so)

### 7.父子通信props

  

![[attachments/Untitled 17 6.png|Untitled 17 6.png]]

  

![[attachments/Untitled 18 6.png|Untitled 18 6.png]]

  

![[attachments/Untitled 19 6.png|Untitled 19 6.png]]

  

![[attachments/Untitled 20 6.png|Untitled 20 6.png]]

### 8.跨组件通信inject provide

  

![[attachments/Untitled 21 6.png|Untitled 21 6.png]]

  

![[attachments/Untitled 22 6.png|Untitled 22 6.png]]

  

### 9.defineOptions

  

![[attachments/Untitled 23 6.png|Untitled 23 6.png]]

  

![[attachments/Untitled 24 6.png|Untitled 24 6.png]]

  

  

### 10.v-model 和 defineModel

  

![[attachments/Untitled 25 6.png|Untitled 25 6.png]]

  

![[attachments/Untitled 26 6.png|Untitled 26 6.png]]

### 11.Pinia是什么

  

![[attachments/Untitled 27 6.png|Untitled 27 6.png]]

  

  

  

### 12.Pinia基础语法

  

![[attachments/Untitled 28 6.png|Untitled 28 6.png]]

  

![[attachments/Untitled 29 6.png|Untitled 29 6.png]]

  

![[attachments/Untitled 30 6.png|Untitled 30 6.png]]

  

![[attachments/Untitled 31 6.png|Untitled 31 6.png]]

  

![[attachments/Untitled 32 6.png|Untitled 32 6.png]]

  

![[attachments/Untitled 33 6.png|Untitled 33 6.png]]

### 13Vue插件

![[attachments/Untitled 34 6.png|Untitled 34 6.png]]

![[attachments/Untitled 35 6.png|Untitled 35 6.png]]
---
date_created: 2024-04-2日 星期二 , 09:59:38 上午
date_modified: 2024-04-2日 星期二 , 10:03:57 上午
---

# Vue3: 如何在 ref() 与 reactive() 之间做正确选择？

[zhangbao90s](https://juejin.cn/user/1363050148666824/posts)
专栏： 

Vue

> 原文地址：[Ref() vs Reactive() in Vue 3 — what’s the right choice?](https://link.juejin.cn/?target=https%3A%2F%2Fmedium.com%2F%40bsalwiczek%2Fref-vs-reactive-in-vue-3-whats-the-right-choice-7c6f7265ce39 "https://medium.com/@bsalwiczek/ref-vs-reactive-in-vue-3-whats-the-right-choice-7c6f7265ce39")，2022.01.29，by Bartosz Salwiczek

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/79454f0908b746798cd4799cb851005f~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

Composition API 提供了两种在组件中引入响应式状态的方式。因此，你需要在 `ref()`、`reactive()` 之间决定使用哪一个，或是两者都用。本文将帮助你做出正确的选择，但让我们先快速介绍一下这两种方式。

## 快速介绍

`ref()` 和 `reactive()` 用于跟踪其参数的更改。当使用它们初始化变量时，是向 Vue 提供信息：“嘿，每次这些变量发生更改时，请重新构建或重新运行依赖于它们的所有内容”。

在下面的示例中，单击按钮后 `personRef` 和 `personReactive` 都会修改 `name` 属性，随后便会在 UI 上得到响应，但对普通 JS 对象 `person` 来说就不会。

<template>
  {{ person.name }} <!-- 不会变为 Amy -->
  {{ personRef.name }} <!-- 会变为 Amy -->
  {{ personReactive.name }} <!-- 会变为 Amy -->
  <button @click="changeName('Amy')">Change Name</button>
</template>
```vue
<script setup lang="ts">
  import { ref, reactive } from 'vue'

  const person = { name: 'John' }
  const personRef = ref({ name: 'John' })
  const personReactive = reactive({ name: 'John' })

  const changeName = (name: string) => {
    person.name = name
    personRef.value.name = name
    personReactive.name = name
  }
</script>
```

基本上，它们用于[让组件具有响应性](https://link.juejin.cn/?target=https%3A%2F%2Fv3.vuejs.org%2Fguide%2Freactivity.html%23what-is-reactivity "https://v3.vuejs.org/guide/reactivity.html#what-is-reactivity")（对变化做出反应）。

## 不同之处

`ref()` 与 `reactive()` 主要有三个区别：

- `ref()` 函数可以接受[原始类型](https://link.juejin.cn/?target=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FGlossary%2FPrimitive "https://developer.mozilla.org/en-US/docs/Glossary/Primitive")（最常见的是布尔值、字符串和数字）以及对象作为参数，而 `reactive()` 函数只能接受对象作为参数。

```js
// 无效
const x = reactive(true)

// 有效
const x = ref(true)

```
对于对象，这两种语法都是有效的：
```js
// 有效
const x = reactive({ name: 'John'})

// 有效
const x = ref({ name: 'John'})

```
- `ref()` 有一个 `.value` 属性，你必须使用 `.value` 属性获取内容，但是使用 `reactive()` 的话可以直接访问：
```js
// 有效
const x = reactive({ name: 'John'})
x.name = 'Amy'
// x => { name: 'Ammy' }

// 有效
const x = ref({ name: 'John'})
x.value.name = 'Amy'
// x.value => { name: 'Ammy' }

```

> 注意：`ref`s 传递到模板（`<template>`）时，会被解包，因此你不需要在那里写 `.value`。

- 使用 `ref()` 函数可以替换整个对象实例，但是在使用 `reactive()` 函数时就不行：

```js
// 无效 - x 的更改不会被 Vue 记录
let x = reactive({name: 'John'})
x = reactive({todo: true})

// 有效
const x = ref({name: 'John'})
x.value = {todo: true}

```

## 为什么同时存在 `ref()`、`reactive()`？

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/23b5498ecf674eb29cfd3d2c3bbf4271~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

看起来 `reactive()` 只是 `ref()` 的一个限制版本，那么还需要在代码中考虑使用 `reactive()` 吗？为什么不总是使用 `ref()`？

我深入了解了下 Vue 3 团队为什么要暴露 `reactive()` 给我们，而不是把它作为内部方法、不提供给 Vue 程序员使用的原因。

最后...发现有一种用例，使用 `reactive()` 胜过 `ref()`。

## 改变观点

在此之前，让我们查看 Vue.js 源代码，更好地理解响应式方法之间的关系。

下面是 Vue.js 3 中 [ref() 实现](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Fvuejs%2Fcore%2Fblob%2Fmain%2Fpackages%2Freactivity%2Fsrc%2Fref.ts "https://github.com/vuejs/core/blob/main/packages/reactivity/src/ref.ts")的部分代码：
```ts
class RefImpl<T> {
	private _value: T
  private _rawValue: T

  public dep?: Dep = undefined
  public readonly __v_isRef = true

  constructor(value: T, public readonly __v_isShallow: boolean) {
    this._rawValue = __v_isShallow ? value : toRaw(value)
    this._value = __v_isShallow ? value : toReactive(value)
  }

  get value() {
    trackRefValue(this)
    return this._value
  }

  set value(newVal) {
    newVal = this.__v_isShallow ? newVal : toRaw(newVal)
    if (hasChanged(newVal, this._rawValue)) {
      this._rawValue = newVal
      this._value = this.__v_isShallow ? newVal : toReactive(newVal)
      triggerRefValue(this, newVal)
    }
  }
}

```

在第 8 行中，我们每次写 `ref(x)` 时都会调用一个构造函数。其中发生了一些有趣的事情。

在第 10 行中，调用了 `toReactive(x)`，它只是一个将对象更改为 `reactive()` 的函数！

**结论**：`ref()` 在背后就是使用的 `reactive()`，你可以把 `ref()` 简单看成：

```ts
const myRef = reactive({
  value: "I'm ref!"
})

myRef.value // "I'm ref!"
myRef.value = 'Changed'
myRef.value // "Changed"

```

## 什么情况下使用 `reactive()` 更好？

使用 `reactive()` 的一个优点是避免样板代码。当使用 `ref`s 时，你可能会因为在代码中到处写 `.value` 而感到烦恼。但是，如果需要原始值，则无法避免 `ref()` 的使用……除非将它们放入对象中！

事实证明，在想要将整个状态放入一个变量中时，`reactive()` 非常方便，就像在选项 API（`data()`）中所做的那样。对比 `ref`，`reactive()` 会跟踪每个属性的变动。

**这意味着在 `reactive()` 中的每个属性都会被视为独立的 `ref()`**, Vue 会据此确定是否需要更新某些依赖于这些属性的内容。

**如果想将 `ref()` 用作状态容器，每当一个属性更新时，使用该状态的任何地方都将被更新。这会触发不必要的重新渲染并减慢应用程序的速度。**

以下是使用一个状态变量示例：

```js
const state = reactive({
  person: {name: 'John'},
  isLoading: false,
  updated: true,
  ...
})

```

**结论**：你可以将 `reactive()` 看作未包装的 `ref()` 容器。如果你想要一个单状态变量，可以在组件内部使用它。

## 最后的说明

`ref()` 和 `reactive()` 在开始时可能看起来非常相似，但它们的目的略有不同。关于这个话题没有好的编程实践，所以一切都取决于你和你的团队如何决定。

在我看来，**你应该盲目地选择 `ref()` 而不是 `reactive()`**。这样代码风格会更加一致，并且你也不需要考虑使用哪一个——编码速度会稍微快一些。使用 `.value` 访问变量可能会使你感到烦恼，但我认为这可以作为变量是响应性变量的一个标识。使用 `reactive()` 我们会失去这些信息，必须检查变量定义。

但请记住一个特殊用例，如果你喜欢组件内部状态仅有一个变量，那么 `reactive()` 就是适合你的正确工具。
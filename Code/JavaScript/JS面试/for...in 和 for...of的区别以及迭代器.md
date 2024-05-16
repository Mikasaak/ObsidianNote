---
description: 
pubDate:
tags: 
title: for...in 和 for...of的区别以及迭代器
date_created: 2024-04-23日 星期二 , 03:25:23 下午
date_modified: 2024-04-28日 星期日 , 02:13:21 下午
---
### for...in 和 for...of的区别


#### for...in
**for...in是遍历可枚举属性 可以遍历object会遍历到原型链上不属于自己本身的属性**

该循环将迭代对象本身的所有可枚举属性，以及对象从其原型链继承的属性（原型链中较近的原型的属性优先于较远的原型的属性）。

可以通过Object.defineProperty()方法进行设置对象的可枚举属性
```js
const object1 = {};

Object.defineProperty(object1, 'property1', {
  value: 42,
  enumerable:true
});
```

可以通过 Object.prototype.propertyIsEnumerable()对对象的某个属性
```js
const object1 = {};
const array1 = [];
object1.property1 = 42;
array1[0] = 42;

console.log(object1.propertyIsEnumerable('property1'));
// Expected output: true

console.log(array1.propertyIsEnumerable(0));
// Expected output: true

console.log(array1.propertyIsEnumerable('length'));
// Expected output: false
```



#### for...of
for...of是遍历可迭代对象
**`for...of`** 语句执行一个循环，该循环处理来自[可迭代对象](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E5%8F%AF%E8%BF%AD%E4%BB%A3%E5%8D%8F%E8%AE%AE)的值序列。可迭代对象包括内置对象的实例，例如 [`Array`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array)、[`String`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String)、[`TypedArray`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/TypedArray)、[`Map`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Map)、[`Set`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Set)、[`NodeList`](https://developer.mozilla.org/zh-CN/docs/Web/API/NodeList)（以及其他 DOM 集合），还包括 [`arguments`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Functions/arguments) 对象、由[生成器函数](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/function*)生成的[生成器](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Generator)，以及用户定义的可迭代对象。

#### [描述](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/for...of#%E6%8F%8F%E8%BF%B0)

`for...of` 循环按顺序逐个处理从可迭代对象获取的值。循环对值的每次操作被称为一次_迭代_，而循环本身被称为_迭代可迭代对象_。每次迭代都会执行可能引用当前序列值的语句。

当 `for...of` 循环迭代一个可迭代对象时，它首先调用可迭代对象的 [`[@@iterator]()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Symbol/iterator) 方法，该方法返回一个[迭代器](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E8%BF%AD%E4%BB%A3%E5%99%A8%E5%8D%8F%E8%AE%AE)，然后重复调用生成器的 [`next()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E8%BF%AD%E4%BB%A3%E5%99%A8%E5%8D%8F%E8%AE%AE) 方法，以生成要分配给 `variable` 的值的序列。

`for...of` 循环在迭代器完成时退出（即迭代器的 `next()` 方法返回一个包含 `done: true` 的对象）。你也可以使用控制流语句来改变正常的控制流程。[`break`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/break) 语句退出循环并跳转到循环体后的第一条语句，而 [`continue`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/continue) 语句跳过当前迭代的剩余语句，继续进行下一次迭代。

如果 `for...of` 循环提前退出（例如遇到 `break` 语句或抛出错误），则会调用迭代器的 [`return()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E8%BF%AD%E4%BB%A3%E5%99%A8%E5%8D%8F%E8%AE%AE) 方法来执行任何清理任务。

`for...of` 的 `variable` 部分可以接受任何在 = 运算符之前的内容。只要在循环体内部不重新赋值（可以在迭代之间更改，因为它们是两个独立的变量），你可以使用 [`const`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/const) 来声明变量。否则，你可以使用 [`let`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/let)。

![[迭代协议,迭代器]]
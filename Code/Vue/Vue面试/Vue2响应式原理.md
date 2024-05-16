---
description: 
pubDate:
tags: 
title: Vue2响应式原理
date_created: 2024-05-4日 星期六 , 05:31:59 下午
date_modified: 2024-05-4日 星期六 , 05:32:12 下午
---
虽然Vue3已经正式发布，但目前Vue2还是开发主力，所以近期面试Vue2相关内容还是比较常见的，今天我们一起来看看下面这个问题：

## **面试题**

> 面试官：说一说你对Vue2 响应式原理的理解？  

## **无法让面试官满意的回答**

碰到面试官问你这个问题，你可能会做如下回答：

> Vue是非侵入性的响应式系统，遍历对象并使用Object.defineProperty对对象的属性进行数据劫持，当数据发生变化时，触发数据劫持的setter函数，通知组件实例的watcher需要进行视图更新，以此来实现响应式。  

上面的答案虽然提到 `Object.defineProperty` 这一关键点，但并不能让面试官满意，因为有一些关键的细节并没有回答出来，比如：Vue是在什么时候进行数据劫持？又是如何实现在数据更新时通知视图更新的？

## **让面试官满意的回答**

下面我们一起来过一下Vue2 的响应式流程：

- 在`init`数据初始化的时候，对象内部通过 `defineReactive` 方法，使用 `Object.defineProperty` 将属性进行劫持（这时候只会劫持已经存在的属性）。如果数据是数组类型， Vue2中是通过重写数组方法来实现。多层对象是通过递归来实现劫持的。  
    
- 在初始化流程中的编译阶段，当`render function` 被渲染的时候，会读取Vue实例中和视图相关的响应式数据，此时会触发 `getter` 函数进行 **依赖收集**（将观察者`Watcher`对象存放到当前闭包的订阅者`Dep`的`subs`中），此时的数据劫持功能和观察者模式就实现了一个MVVM模式中的Binder，之后就是正常的渲染和更新流程。  
    
- 当数据发生变化或者视图导致的数据发生变化时，会触发数据劫持的`setter`函数，`setter`会通知初始化依赖收集中的`Dep`中和视图相应的 `Watcher` ，告知需要重新渲染视图，`Watcher` 就会再次通过 `update` 方法来更新视图。  
    

上面的回答基本将Vue2的响应式原理说清楚了，虽然还有一些细节的内容没说，但如果你们清晰的将上面三个流程说出来，面试官就能知道你已经理解了Vue2的响应式原理，面试评分自然不会低。





# 如何理解vue数据双向绑定原理

Vue数据双向绑定原理是通过数据劫持结合发布者-订阅者模式的方式来实现的，首先是对数据进行监听，然后当监听的属性发生变化时则告诉订阅者是否要更新，若更新就会执行对应的更新函数从而更新视图

![](https://pic2.zhimg.com/v2-10f94b6de4ff367903ea4c8c8aa6e865_r.jpg)

[web前端学习：web前端全栈资料粉丝福利（面试题、视频、资料笔记，进阶路线）​zhuanlan.zhihu.com/p/136454207](https://zhuanlan.zhihu.com/p/136454207)

## **MVC模式**  

以往的MVC模式是单向绑定，即Model绑定到View，当我们用JavaScript代码更新Model时，View就会自动更新

  

![](https://pic3.zhimg.com/v2-379cb77a473bf0c7c449f701b8a17ffe_r.jpg)

  

## **MVVM模式**

MVVM模式就是Model–View–ViewModel模式。它实现了View的变动，自动反映在 ViewModel，反之亦然。对于双向绑定的理解，就是用户更新了View，Model的数据也自动被更新了，这种情况就是双向绑定。再说细点，就是在单向绑定的基础上给可输入元素input、textare等添加了change(input)事件,(change事件触发，View的状态就被更新了)来动态修改model。

  

![](https://pic3.zhimg.com/v2-10c092ce5f24e44625165228cd4f245e_r.jpg)

  

## **双向绑定原理**

vue数据双向绑定是通过数据劫持结合发布者-订阅者模式的方式来实现的

我们已经知道实现数据的双向绑定，首先要对数据进行劫持监听，所以我们需要设置一个监听器Observer，用来监听所有属性。如果属性发上变化了，就需要告诉订阅者Watcher看是否需要更新。因为订阅者是有很多个，所以我们需要有一个消息订阅器Dep来专门收集这些订阅者，然后在监听器Observer和订阅者Watcher之间进行统一管理的。接着，我们还需要有一个指令解析器Compile，对每个节点元素进行扫描和解析，将相关指令（如v-model，v-on）对应初始化成一个订阅者Watcher，并替换模板数据或者绑定相应的函数，此时当订阅者Watcher接收到相应属性的变化，就会执行对应的更新函数，从而更新视图。

**因此接下去我们执行以下3个步骤，实现数据的双向绑定：**

- （1）实现一个监听器Observer，用来劫持并监听所有属性，如果有变动的，就通知订阅者。
- （2）实现一个订阅者Watcher，每一个Watcher都绑定一个更新函数，watcher可以收到属性的变化通知并执行相应的函数，从而更新视图。
- （3）实现一个解析器Compile，可以扫描和解析每个节点的相关指令（v-model，v-on等指令），如果节点存在v-model，v-on等指令，则解析器Compile初始化这类节点的模板数据，使之可以显示在视图上，然后初始化相应的订阅者（Watcher）。

![](https://pic3.zhimg.com/v2-f356f2023758b0a503e4200596f941de_r.jpg)

## **实现一个Observer**

Observer是一个数据监听器，其实现核心方法就是Object.defineProperty( )。如果要对所有属性都进行监听的话，那么可以通过递归方法遍历所有属性值，并对其进行Object.defineProperty( )处理  
如下代码实现了一个Observer。

  

```js
function Observer(data) {    this.data = data;    this.walk(data);
}
 
Observer.prototype = {    walk: function(data) {        
var self = this;        //这里是通过对一个对象进行遍历，对这个对象的所有属性都进行监听
 Object.keys(data).forEach(function(key) {
 self.defineReactive(data, key, data[key]);
 });
 },    defineReactive: function(data, key, val) {        
 var dep = new Dep();      // 递归遍历所有子属性
 var childObj = observe(val);        
 Object.defineProperty(data, key, {            
 enumerable: true,            
 configurable: true,            
 get: function getter () {                
 if (Dep.target) {                  
 // 在这里添加一个订阅者
 console.log(Dep.target)
 dep.addSub(Dep.target);
 }                return val;
 },           
 // setter，如果对一个对象属性值改变，就会触发setter中的dep.notify(),
 通知watcher（订阅者）数据变更，执行对应订阅者的更新函数，来更新视图。
 set: function setter (newVal) {                
 if (newVal === val) {                    
 return;
 }
 val = newVal;              
 // 新的值是object的话，进行监听
 childObj = observe(newVal);
 dep.notify();
 }
 });
 }
};function observe(value, vm) {    if (!value || typeof value !== 'object') {        
return;
 }    return new Observer(value);
};// 消息订阅器Dep，订阅器Dep主要负责收集订阅者，然后在属性变化的时候执行对应订阅者的更新函数
function Dep () {    
this.subs = [];
}
Dep.prototype = {  /**
 * [订阅器添加订阅者]
 * @param  {[Watcher]} sub [订阅者]
 */
 addSub: function(sub) {        
 this.subs.push(sub);
 },  // 通知订阅者数据变更
 notify: function() {        
 this.subs.forEach(function(sub) {
 sub.update();
 });
 }
};
Dep.target = null;
```

在Observer中，当初我看别人的源码时，我有一点不理解的地方就是`Dep.target`是从哪里来的，相信有些人和我会有同样的疑问。这里不着急，当写到Watcher的时候，你就会发现，这个`Dep.target`是来源于Watcher。

## **实现一个Watcher**

Watcher就是一个订阅者。用于将Observer发来的update消息处理，执行Watcher绑定的更新函数。

**如下代码实现了一个Watcher**

  

```js
function Watcher(vm, exp, cb) {    
this.cb = cb;    
this.vm = vm;    
this.exp = exp;    
this.value = this.get();  // 将自己添加到订阅器的操作}
 
Watcher.prototype = {    update: function() {        
this.run();
 },    run: function() {        
 var value = this.vm.data[this.exp];        
 var oldVal = this.value;        
 if (value !== oldVal) {            
 this.value = value;            
 this.cb.call(this.vm, value, oldVal);
 }
 },    get: function() {
 Dep.target = this;  // 缓存自己
 var value = this.vm.data[this.exp]  // 强制执行监听器里的get函数
 Dep.target = null;  // 释放自己
 return value;
 }
};
```

在我研究代码的过程中，我觉得最复杂的就是理解这些函数的参数，后来在我输出了这些参数之后，函数的这些功能也容易理解了。vm，就是之后要写的SelfValue对象，相当于Vue中的new Vue的一个对象。exp是node节点的v-model或`v-on：click`等指令的属性值。

上面的代码中就可以看出来，在Watcher的getter函数中，`Dep.target`指向了自己，也就是Watcher对象。在getter函数中，

  

```text
var value = this.vm.data[this.exp]  // 强制执行监听器里的get函数。
这里获取vm.data[this.exp] 时，会调用Observer中Object.defineProperty中的get函数
get: function getter () {                
if (Dep.target) {                  
// 在这里添加一个订阅者                  
console.log(Dep.target)                    
dep.addSub(Dep.target);                
}                
return val;            
},
```

从而把watcher添加到了订阅器中，也就解决了上面`Dep.target`是哪里来的这个问题。

## **实现一个Compile**

Compile主要的作用是把new SelfVue 绑定的dom节点，（也就是el标签绑定的id）遍历该节点的所有子节点，找出其中所有的v-指令和" {{}} ".

- （1）如果子节点含有v-指令，即是元素节点，则对这个元素添加监听事件。（如果是v-on，则`node.addEventListener('click'）`，如果是v-model，则`node.addEventListener('input'))`。接着初始化模板元素，创建一个Watcher绑定这个元素节点。
- （2）如果子节点是文本节点，即" {{ data }} ",则用正则表达式取出" {{ data }} "中的data，然后`var initText = this.vm[exp]`，用initText去替代其中的data。

## **实现一个MVVM**

可以说MVVM是Observer，Compile以及Watcher的“boss”了，他需要安排给Observer，Compile以及Watche做的事情如下

- （1）Observer实现对MVVM自身model数据劫持，监听数据的属性变更，并在变动时进行notify  
    （2）Compile实现指令解析，初始化视图，并订阅数据变化，绑定好更新函数  
    （3）Watcher一方面接收Observer通过dep传递过来的数据变化，一方面通知Compile进行view update。  
    最后，把这个MVVM抽象出来，就是vue中Vue的构造函数了，可以构造出一个vue实例。

## 最后写一个html测试一下我们的功能

  

```text
<!DOCTYPE html><html lang="en"><head>
 <meta charset="UTF-8">
 <title>self-vue</title></head><style>
 #app {        
 text-align: center;
 }</style><body>
 <div id="app">
 <h2>{{title}}</h2>
 <input v-model="name">
 <h1>{{name}}</h1>
 <button v-on:click="clickMe">click me!</button>
 </div></body><script src="js/observer.js"></script>
 <script src="js/watcher.js"></script>
 <script src="js/compile.js"></script>
 <script src="js/mvvm.js"></script>
 <script type="text/javascript">
 var app = new SelfVue({        
 el: '#app',        
 data: {            
 title: 'hello world',            
 name: 'canfoo'
 },        
 methods: {            
 clickMe: function () {                
 this.title = 'hello world';
 }
 },        
 mounted: function () {            
 window.setTimeout(() => {                
 this.title = '你好';
 }, 1000);
 }
 });</script></html>
```

**先执行mvvm中的new SelfVue(...)，在mvvm.js中，**

```text
observe(this.data);
new Compile(options.el, this);
```

先初始化一个监听器Observer，用于监听该对象data属性的值。  
然后初始化一个解析器Compile，绑定这个节点，并解析其中的v-，" {{}} "指令，（每一个指令对应一个Watcher）并初始化模板数据以及初始化相应的订阅者，并把订阅者添加到订阅器中（Dep）。这样就实现双向绑定了。  
**如果v-model绑定的元素，**

```text
<input v-model="name">
```

**即输入框的值发生变化，就会触发Compile中的**

```text
node.addEventListener('input', function(e) {            
var newValue = e.target.value;            
if (val === newValue) {                
return;
 }            
 self.vm[exp] = newValue;
 val = newValue;
 });
```

`self.vm[exp] = newValue;`这个语句会触发mvvm中SelfValue的setter，以及触发Observer对该对象name属性的监听，即Observer中的`Object.defineProperty（）`中的setter。setter中有通知订阅者的函数`dep.notify`,Watcher收到通知后就会执行绑定的更新函数。  
最后的最后就是效果图啦：

  

![动图封面](https://pic4.zhimg.com/v2-23770e5bcfad60ce53217646e99a5917_b.jpg)

  

以上就是如何理解vue数据双向绑定原理的详细内容，更多请关注我！！！！！！！
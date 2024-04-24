---
description: 
pubDate:
tags: 
title: 事件循环-CSDN
date_created: 2024-04-24日 星期三 , 07:35:08 晚上
date_modified: 2024-04-24日 星期三 , 07:35:43 晚上
---
## 为什么要采用[EventLoop](https://so.csdn.net/so/search?q=EventLoop&spm=1001.2101.3001.7020)

### 1. 为什么JS是单线程语言？

​ JS的单线程是因为他是一个浏览器脚本语言，他的主要用途是与用户互动以及操作DOM，如果JS是多线程语言，那么一个线程新增DOM一个线程删除了该DOM，浏览器将以哪个线程为准呢？所以为了避免复杂性和各种冲突就采用了单线程方式。此后**H5为了利用多核心CPU的计算能力，提出了web worker标准，允许JS创建多个线程，但子线程完全受主线程控制且不能操作DOM**。

### 2. 任务队列

​ JS是单线程语言，在程序执行时只有一个线程，如果程序是读取文件，发送网络请求或者处理I/O事件的话，线程等待的时间会很长，这段时间内浏览器窗口将会卡死。

所以JS开了一个新线程，就叫**eventloop线程**，一个主线程负责程序本身的运行，一个负责主线程与**其他线程**（I/O操作等等）的通信，被称为eventloop线程。

​ JS设计者意识到可以完全不管IO设备，将等待中的任务挂起，先运行排在后面的任务，等到IO设备返回时再将任务继续执行下去。

​ 于是乎JS的任务就分为了两种：**同步任务、异步任务**。同步任务指的是在主线程上排队执行的任务，只有前一个任务执行完毕，下一个任务才可以执行；异步任务指的是不进入主线程，而进入任务队列的任务，只有在任务队列通知主线程，某个任务可以执行了，该任务才会被进入主线程执行。

> （1）所有同步任务都在主线程上执行，形成一个[执行栈](https://www.ruanyifeng.com/blog/2013/11/stack.html)（execution context stack）。
> 
> （2）主线程之外，还存在一个"任务队列"（task queue）。只要异步任务有了运行结果，就在"任务队列"之中放置一个事件。
> 
> （3）一旦"执行栈"中的所有同步任务执行完毕，系统就会读取"任务队列"，看看里面有哪些事件。那些对应的异步任务，于是结束等待状态，进入执行栈，开始执行。
> 
> （4）主线程不断重复上面的第三步。

![](https://img-blog.csdnimg.cn/img_convert/58dc5242a10fa6b4ffab787b5b069a66.png)![img](https://img-blog.csdnimg.cn/img_convert/f6174c53bfc6e65e68d3fbce187c3e31.png)

> ​ 上图主线程的绿色部分，还是表示运行时间，而橙色部分表示空闲时间。每当遇到I/O的时候，主线程就让Event Loop线程去通知相应的I/O程序，然后接着往后运行，所以不存在红色的等待时间。等到I/O程序完成操作，Event Loop线程再把结果返回主线程。主线程就调用事先设定的回调函数，完成整个任务。
> 
> ​ 可以看到，由于多出了橙色的空闲时间，所以主线程得以运行更多的任务，这就提高了效率。这种运行方式称为"[异步模式](https://en.wikipedia.org/wiki/Asynchronous_I/O)"（asynchronous I/O）或"非堵塞模式"。
> 
> ​ 这正是JavaScript语言的运行方式。单线程模型虽然对JavaScript构成了很大的限制，但也因此使它具备了其他语言不具备的优势。如果部署得好，JavaScript程序是不会出现堵塞的，这就是为什么node.js平台可以用很少的资源，应付大流量访问的原因。

### 3. 事件和回调函数

​ 任务队列是一个事件的队列，IO设备完成一项任务，就在任务队列添加一个事件，表示相关的异步任务可以进入执行栈了。主线程读取任务队列，就是读取里面有哪些事件

​ 任务队列中的事件，除了IO设备的事件意外，还包括一些用户产生的是事件（比如鼠标点击，页面滚动等等），只要制定了回调函数，这些事件发生时就会进入任务队列等待主线程读取

​ 所谓回调函数就是被主线程挂起来等着的代码。异步任务必须指定回调函数，当主线程开始执行异步任务就是开始执行对应的回调函数

​ 任务队列是一个先进先出的数据结构（栈），排在前面的事件优先被主线程读取，主线程读取过程基本是自动的，执行栈一清空就从任务队列里读取最先加进来的任务执行，但是由于存在**定时器（setTimeout）**这一功能，某些任务只有到了规定的时间才能返回主线程。

### 4. **Event Loop**

​ 主线程从"任务队列"中读取事件，这个过程是循环不断的，所以整个的这种运行机制又称为Event Loop（事件循环）。

![](https://img-blog.csdnimg.cn/img_convert/3985bcf9c2a1be54bc4559e11645a2ee.png)

​ 上图中，主线程运行的时候，产生堆（heap）和栈（stack），栈中的代码调用各种外部API，它们在"任务队列"中加入各种事件（click，load，done）。只要栈中的代码执行完毕，主线程就会去读取"任务队列"，依次执行那些事件所对应的回调函数。堆中存储对象、数组、函数、字符串、正则表达式和 Date 等需要动态分配的数据。

​ 执行栈中的代码（同步任务），总是在读取"任务队列"（异步任务）之前执行。请看下面这个例子。

```javascript
var req = new XMLHttpRequest();
req.open('GET', url);    
req.onload = function (){};    
req.onerror = function (){};    
req.send();
```

​ 上面代码中的`req.send`方法是Ajax操作向服务器发送数据，它是一个异步任务，意味着只有当前脚本的所有代码执行完，系统才会去读取"任务队列"。所以，它与下面的写法等价。

```javascript
var req = new XMLHttpRequest();
req.open('GET', url);
req.send();
req.onload = function (){};    
req.onerror = function (){};   
```

​ 也就是说，指定回调函数的部分（onload和onerror），在send()方法的前面或后面无关紧要，因为它们属于执行栈的一部分，系统总是执行完它们，才会去读取"任务队列"。

#### 4.1 事件循环里的宏任务和微任务

**宏任务（执行优先级：用户交互事件 > DOM操作{DOM改变可能导致重绘和回流} > UI渲染 > 定时器 > 网络请求等I/O任务）：**

> - script(整体代码)
> - setTimeout
> - setInterval
> - setImmediate
> - I/O
> - UI 渲染
> - DOM 事件
> - HTTP 响应

​ 定时器：**setTimeout(回调函数，延迟时间)**、**setInterval(回调函数，延迟时间)**，如果将第二个参数设为0，就表示当前代码执行完（执行栈清空）以后立即执行指定的回调函数

**微任务：**

> - process.nextTick()
> - Promise的各种方法，例如promise.then() .catch() .finally()
> - Async/Await(实际就是promise)
> - MutationObserver(html5新特性)

#### 4.2 执行顺序

存在**宏任务队列、微任务队列、执行栈**，当代码执行时先按照以下步骤：

1. 遍历代码：将同步代码压入调用堆栈，执行同步代码。直到调用堆栈为空。
2. 运行宏任务队列中的第一个宏任务
3. 运行所有微任务：从微任务队列中选择最早的微任务，并将其压入执行栈，如果此过程中产生了新的微任务，则将新的微任务压入微任务队列。重复该步骤直到微任务队列为空。
4. UI渲染：重新呈现 UI。
5. 返回到步骤 2：从宏任务队列里读取第一个宏任务执行进入下一个事件循环。

总的结论就是，**执行宏任务 => 遇到宏任务的函数就放到任务队列里然后继续执行同步代码 => 执行该宏任务产生的微任务 => 若微任务在执行过程中产生了新的微任务 => 则继续执行微任务 => 微任务执行完毕后 => UI渲染 => 回到宏任务队列中读取下一个宏任务中进行下一轮循环**。

![事件循环执行机制](https://img-blog.csdnimg.cn/img_convert/928f306d1f22a47fb0ec1f0c5aae7650.png)

##### 4.2.1 **async/await执行顺序**

​ `async`隐式返回 Promise 作为结果的函数,那么可以简单理解为，`await`后面的函数执行完毕时，`await`会产生一个微任务(`Promise.then`是微任务)。但是我们要注意这个微任务产生的时机，它是执行完`await`之后，直接跳出`async`函数，执行其他代码(此处就是协程的运作，A暂停执行，控制权交给B)。其他代码执行完毕后，再回到`async`函数去执行剩下的代码，然后把`await`后面的代码注册到微任务队列当中。

​ 执行到`await`时，`await`会阻塞下面的代码，会先等到`await`右边跟着的表达式的结果，就是`await`等待的东西。等到之后，对于`await`来说，也分两种情况，一种是等到的是一个`promise`对象，另一种是非`promise`对象。

​ 不是`promise`对象（下面例子的`async2函数`没有返回结果，所以`async1函数`被挂起了），`await`会阻塞下面的代码，先执行`async`外面的同步代码，等同步代码执行完之后，再回到async内部，把这个非`promise`的东西，作为`await`表达式的结果。如果await等是一个promise对象，`await`也会阻塞`async`下面的代码，先执行`async`外面的同步代码，等`promise`对象`fulfilled`，然后把`resolve`的参数作为`await`表达式的运算结果。

##### 4.2.2 **promise 概述**：

promise 就是一种状态机的实现，有三种状态：`pending（执行中）、fulfilled（成功状态/已完成状态）、rejected（失败状态）`。

我们在`new Promise()`时（此时的状态为pending），需要传入的函数有两个参数，一个`resolve()`，一个`reject()`，这两个参数分别负责promise状态的改变（分别对应成功和失败）。

当promise状态为成功时，可以按顺序执行他的`then()`方法，当状态为失败时，不会执行`then()`方法，而是执行他的`catch()`方法，当`then或者catch`被执行完之后执行`finall()`方法。

**Promise API：promise的 .all([p1, p2, …]) 和 .race([p1, p2, …]) 区别**

> 这两个方法都是传入一个数组，这个数组中的参数全部为 promise 对象
> 
> 当`.all([p1, p2, ...])`中的p1,p2等的 promise 状态全部为fulfilled（成功状态）时，`.all().then()`回调才会执行，否则将跳过
> 
> 当`.race([p1, p2, ...])`这些参数中有一个状态为 fulfilled 时，就会执行后面的`then()`回调
> 
> `all()`用于等待多个异步任务完成，例如：等待多个接口返回数据然后进行计算
> 
> `race()`用于快速响应情形，例如：从多个接口获取数据但是响应数据之间没有关联关系，无需等待所有请求返回，只返回一个数据就可以进行页面加载

##### 4.2.3 **定时器概述：setTimeout/setInterval（两个函数除执行次数外几乎相同，所以只讲setTimeout）**

`setTimeOut`执行需要满足两个条件：

1. 主进程必须是空闲的状态，如果到时间了，主进程不空闲也不会执行你的回调函数
2. 这个回调函数需要等到插入异步队列时前面的异步函数都执行完了，才会执行

**注意：** `setTimeOut`并不是直接的把回调函数放进异步队列中，而是**在定时器的时间到了之后，把回调函数放到执行异步队列中去**。如果此时这个队列已经有很多任务了，那就排在他们的后面。这也就解释了为什么setTimeOut为什么不能精准的执行的问题了。

**补充**：为什么setTimeOut()为什么不能精准的执行？

> ​ `setTimeout` 函数无法精确执行是因为 JavaScript 是单线程执行的，也就是说，在执行 JavaScript 代码时，只有一个线程在工作。当我们调用 `setTimeout` 函数时，它会将要执行的代码放到任务队列中，等到主线程空闲时，才会去执行任务队列中的代码。
> 
> ​ 由于 JavaScript 是单线程执行的，同时还要处理用户交互、网络请求等多种事件，所以当 `setTimeout` 的定时器到期后，可能还有其他代码正在执行，此时 `setTimeout` 中指定的代码就不能立即得到执行。因此，即使我们将 `setTimeout` 中的延迟时间设置为 0，代码仍然不能立即执行。
> 
> ​ `setTimeout` 的定时器并不保证一定会在指定的时间后立即执行，它只保证在指定的时间后将代码添加到任务队列中。由于任务队列中可能还有其他任务在等待执行，因此 `setTimeout` 的实际执行时间可能会比指定的时间晚一些。
> 
> ​ 需要注意的是，`setTimeout` 的执行时间也受到浏览器性能的影响，如果浏览器正在执行一些复杂的操作，可能会导致 `setTimeout` 的执行时间更晚。

##### 4.2.4 例一

```javascript
console.log('script start')

async function async1() {
    await async2()
    console.log('async1 end')
}
async function async2() {
	console.log('async2 end')
}
async1()

setTimeout(function() {
	console.log('setTimeout')
}, 0)

new Promise(resolve => {
    console.log('Promise')
    resolve()
})
.then(function() {
	console.log('promise1')
})
.then(function() {
	console.log('promise2')
})
console.log('script end')
// 旧版输出如下
// script start => async2 end => Promise => script end => promise1 => promise2 => async1 end => setTimeout
// 现在的chorme，因为chrome优化了,await变得更快了
// script start => async2 end => Promise => script end => async1 end => promise1 => promise2 => setTimeout
```

> - 当代码执行到`asyn1`时，执行`await`后面的代码时就将当前的`async1`挂起了(这是因为await async返回promise对象，await如果等到的是个promise对象他就会先挂起当前代码，先执行await代码作为await表达式的结果)，等到`async2`打印`async2 end`以后发现 `async2()` 函数没有返回任何值，因此 `async1()` 函数被挂起先执行后面的同步代码。
>     
> - 然后遇到了定时器函数，这是一个宏任务，创建一个宏任务（以下的代码执行都在这个宏任务环境中，只有这个宏任务中的**同步代码执行完毕之后才会执行微任务**，然后继续下一个宏任务）
>     
> - 遇到创建`promise`，创建对象是同步代码，直接执行，于是乎输出`Promise`并标记当前promise状态为=>已完成
>     
> - 遇到俩`promise.then()`，创建两个微任务，放到微任务队列里，继续读取同步代码，打印`script end`
>     
> - 此时刚才创建的宏任务中的同步代码都执行完毕了，回到被挂起的`async1`函数，打印`async1 end`
>     
> - 执行栈空了，开始读取微任务，打印`promise1`,`promise2`
>     
> - 最后，微任务队列空了，主进程空了，setTimeout的回调函数才进入执行栈开始执行，于是打印`setTimeout`
>     

##### 4.2.5 例二

```javascript
console.log('script start')

async function async1() {
    await async2()
    console.log('async1 end')
}
async function async2() {
    console.log('async2 end')
    return Promise.resolve().then(()=>{
        console.log('async2 end1')
    })
}
async1()

setTimeout(function() {
    console.log('setTimeout')
}, 0)

new Promise(resolve => {
    console.log('Promise')
    resolve()
})
.then(function() {
    console.log('promise1')
})
.then(function() {
    console.log('promise2')
})

console.log('script end')

// script start => async2 end => Promise => script end => async2 end1 => promise1 => promise2 => async1 end => setTimeout
```

> - 先执行同步代码，遇到console.log直接打印 `script start`
> - 执行异步函数asyn1，里面有await async2，这个await等到的是一个promise对象，故async1被挂起
> - 执行async2这个异步函数中的代码，遇到console.log直接打印 `async2 end`，发现这个函数又返回了一个promise.then()，这是个微任务，压入微任务队列
> - 继续执行同步代码，遇到定时器，把定时器的回调放到宏任务队列里，等待下一次事件循环
> - 继续执行同步代码，new promise()直接执行，遇到console.log打印 `Promise`，promise调用了resolve()函数，状态转为fulfilled，故执行then()回调
> - 第一个then()回调压入微任务队列
> - 同步代码继续执行，遇到console.log直接打印 `script end`
> - 到这里同步代码执行完了，开始执行微任务队列里的代码，微任务队列中的代码执行先进先出原则，故async2返回的then()回调被最先执行，打印 `async2 end1`
> - 微任务队列继续执行，发现创建的promise.then()的回调，打印`promise1`，.then()按顺序执行发现后面还有个then回调，将这个then压入微任务队列
> - 执行栈空，继续从微任务队列里读取微任务执行，发现new promise的第二个then回调，打印`promise2`
> - 回到被挂起的async1函数里，将await后面的代码压入执行栈执行，打印`async1 end`
> - 当前执行栈和微任务队列都空了，开始下一次事件循环（在此时进行UI渲染），从宏任务队列里读取优先级最高的任务，发现了定时器的回调，将代码压入执行栈执行，打印`setTimeout`
> - 当前的宏任务队列、微任务队列、执行栈全空，此代码块执行完毕

### 5. **Node.js中的Event Loop**

浏览器中有事件循环，node 中也有，事件循环是 node 处理非阻塞 I/O 操作的机制，node中事件循环的实现是依靠的libuv引擎。由于 node 11 之后，事件循环的一些原理发生了变化，这里就以新的标准去讲，最后再列上变化点让大家了解前因后果。

##### 5.1 **node 和 浏览器 eventLoop的主要区别**

最主要的区别在于**浏览器中的微任务是在每个相应的宏任务中执行**的，而**nodejs中的微任务是在不同阶段之间执行**的。

##### 5.1 **Node中的宏任务和微任务**

node 中也有宏任务和微任务，与浏览器中的事件循环类似。

> 宏任务 大概包括：
> 
> - setTimeout
> - setInterval
> - setImmediate
> - script（整体代码)
> - I/O 操作等。
> 
> **微任务** 大概包括：
> 
> - process.nextTick(与普通微任务有区别，在微任务队列执行之前执行)
> - new Promise().then(回调)等。  
>     务是在不同阶段之间执行**的
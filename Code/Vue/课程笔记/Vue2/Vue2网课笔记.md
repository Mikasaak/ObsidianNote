---
created: 2024-03-31  16:58:07
updated: 2024-03-31  17:04:17
---
官方文档地址：[Vue.js (vuejs.org)](https://v2.cn.vuejs.org/)

  
### 1.VueCli

  

Vue CLI是一个用于创建和管理Vue.js项目的工具，它可以在命令行中访问vue命令。 您可以使用Vue CLI来创建新项目、安装依赖项、运行开发服务器、构建生产版本等等。

如果您想了解更多关于Vue CLI的信息，可以访问Vue CLI官方网站或者GitHub仓库。

  

![[attachments/1000024632 2.png|1000024632 2.png]]

![[attachments/1000024631 2.png|1000024631 2.png]]

![[attachments/1000024633 2.png|1000024633 2.png]]

  

  

### 计算属性与侦听器

  

除了监听响应式对象、嵌套对象和数组的变化外，`**watch**` 还可以监听其他类型的数据。下面是一些 `**watch**` 可以监听的其他类型及其使用场景：

### **1. 监听普通变量**

**解释**：`**watch**` 可以监听普通的 JavaScript 变量，而不仅仅是响应式对象。

**使用场景**：

- 监听普通变量的变化，并在变化时执行相应的操作，例如状态管理中的状态变化。
- 在不使用响应式数据的情况下，需要监听变量的变化并做出相应的响应。

### **2. 监听 getter 函数**

**解释**：`**watch**` 可以监听 getter 函数的返回值，当 getter 函数返回的值发生变化时，回调函数将被触发。

**使用场景**：

- 当需要监听计算属性或派生状态的变化时，可以使用 getter 函数，并通过 `**watch**` 监听其返回值的变化。
- 在复杂的状态管理中，监听 getter 函数的变化来触发相关的逻辑。

### **3. 监听 Promise 或异步操作**

**解释**：`**watch**` 可以监听 Promise 或异步操作的状态变化，例如异步操作的完成或失败。

**使用场景**：

- 监听异步操作的状态变化，并在完成或失败时执行相应的操作，例如数据加载完成后更新 UI。
- 在异步操作完成时执行后续逻辑，例如数据加载完成后执行数据处理操作。

### **4. 监听 ref 对象的变化**

**解释**：`**watch**` 可以监听 ref 对象的变化，包括其值的变化。

**使用场景**：

- 当需要监听单个变量的变化时，可以使用 ref 对象，并通过 `**watch**` 监听其变化。
- 在函数式组件中，通过 `**ref**` 创建的变量可以被 `**watch**` 监听，以执行相关的操作。

### **5. 监听组合式 API 中返回的数据**

**解释**：`**watch**` 可以监听组合式 API 中返回的数据，例如通过 `**setup**` 函数返回的响应式对象或其他数据。

**使用场景**：

- 在 Vue 3 中使用组合式 API 时，可以通过 `**watch**` 监听 `**setup**` 函数返回的数据，以执行相关的操作。
- 在组合式 API 中，可以将需要监听的数据返回给模板，并通过 `**watch**` 监听其变化。

总的来说，`**watch**` 可以监听多种类型的数据变化，包括普通变量、getter 函数、Promise 或异步操作、ref 对象的变化以及组合式 API 中返回的数据等。通过合理地使用 `**watch**`，可以更好地管理应用程序的状态和行为，并确保在数据变化时能够及时做出响应。

  

  

  

![[attachments/Untitled 83.png|Untitled 83.png]]

  

![[attachments/Untitled 1 6.png|Untitled 1 6.png]]

  

  

![[attachments/Untitled 2 7.png|Untitled 2 7.png]]

  

  

  

  

### 深入响应式原理

  

![[attachments/Untitled 3 7.png|Untitled 3 7.png]]

  

  

![[attachments/Untitled 4 7.png|Untitled 4 7.png]]

  

![[attachments/Untitled 5 6.png|Untitled 5 6.png]]

  

  

### 2..组件化开发，组件的定义使用

Vue组件是Vue.js中实现复用和模块化的重要机制。组件的定义使用Vue的单文件组件（SFC）格式，通常以`.vue`为扩展名。一个典型的Vue组件包含模板、脚本和样式三部分。

模板（Template）

模板是组件的HTML结构，用于定义组件的外观和布局。在模板中，可以使用Vue的指令、插值表达式和事件绑定等功能来动态渲染数据和处理用户交互。

```HTML
<template>
  <div class="my-component">
    <h1>{{ message }}</h1>
    <button @click="incrementCounter">点击次数：{{ counter }}</button>
  </div>
</template>
```

在上面的例子中，`<template>`标签内包含了组件的HTML结构，其中使用了双大括号语法`{{ }}`来插入动态数据，以及`@click`指令来监听按钮的点击事件。

脚本（Script）

脚本是组件的逻辑部分，用于定义组件的行为和状态。在脚本中，可以定义组件的数据、方法、计算属性等。

```JavaScript
<script>
export default {
  data() {
    return {
      message: 'Hello, Vue!',
      counter: 0
    };
  },
  methods: {
    incrementCounter() {
      this.counter++;
    }
  }
};
</script>
```

在上面的例子中，`<script>`标签内包含了组件的JavaScript代码，其中使用了`data`函数来定义组件的数据，以及`methods`对象来定义组件的方法。

样式（Style）

样式是组件的外观部分，用于定义组件的布局、颜色、字体等。在样式中，可以使用CSS选择器和Vue的样式绑定功能来设置组件的样式。

```CSS
<style scoped>
.my-component {
  font-size: 16px;
  color: \#333;
}
button {
  background-color: \#4caf50;
  color: white;
  border: none;
  padding: 8px 16px;
  cursor: pointer;
}
button:hover {
  background-color: \#45a049;
}
</style>
```

在上面的例子中，`<style>`标签内包含了组件的CSS样式，其中使用了`scoped`属性来限制样式只应用于当前组件。

综上所述，Vue组件通过模板、脚本和样式三部分的组合来实现数据的展示、交互的处理和样式的定制，从而实现了前端应用的

![[attachments/1000024637 2.png|1000024637 2.png]]

![[attachments/1000024638 2.png|1000024638 2.png]]

![[attachments/1000024639 2.png|1000024639 2.png]]

![[attachments/1000024640 2.png|1000024640 2.png]]

### 3.组件中的data和scoped

在Vue.js中，组件的data和scoped是用于定义组件内部的数据和方法的重要选项。

1. `data`：在Vue组件中，`data`是一个函数，返回一个对象，这个对象包含了该组件的所有数据。这些数据将会被Vue.js观察，并在其内部进行响应式处理。例如：

```JavaScript
export default {
  data() {
    return {
      message: 'Hello Vue!'
    }
  }
}
```

在这个例子中，我们定义了一个名为`message`的数据项，它的初始值是字符串`'Hello Vue!'`。

1. `scoped`：`scoped`是一个布尔值，用于指定是否将样式只应用到当前组件。当设置为`true`时，样式只会应用到当前组件，不会影响到其他组件。这在开发大型单文件组件（.vue文件）时非常有用，因为它可以帮助我们保持组件的封装性和独立性。例如：

```HTML
<template>
  <div class="my-component" scoped>
    <!-- component content -->
  </div>
</template>

<style scoped>
.my-component {
  color: red;
}
</style>
```

在这个例子中，我们为`.my-component`类定义了颜色为红色的样式，这个样式只会应用到当前的`.my-component`组件，不会影响到其他组件。

![[attachments/1000024641 2.png|1000024641 2.png]]

![[attachments/1000024642 2.png|1000024642 2.png]]

### 4.组件通信

在Vue组件中，有多种方式可以进行组件间的通信。其中一种常用的方法是使用事件总线(Event Bus)来进行组件间的通信。

以下是一个示例代码，演示了如何使用事件总线进行组件通信：

```JavaScript
// 创建事件总线实例
const eventBus = new Vue();

// 发送事件
eventBus.$emit('custom-event', data);

// 监听事件
created() {
  eventBus.$on('custom-event', this.handleCustomEvent);
},
beforeDestroy() {
  eventBus.$off('custom-event', this.handleCustomEvent);
},
methods: {
  handleCustomEvent(data) {
    // 处理接收到的数据
    console.log(data);
  }
}
```

在上述代码中，首先通过`new Vue()`创建一个Vue实例，即事件总线。然后可以通过调用`$emit`方法来触发一个自定义事件，并传递数据作为参数。其他组件可以通过监听该事件来接收数据。

在组件的生命周期钩子函数中（例如`created`、`beforeDestroy`），可以使用`$on`方法来注册监听事件，并指定对应的处理方法。当事件被触发时，该方法将被调用，并可以访问传递的数据。最后，在组件销毁之前，需要通过`$off`方法取消对事件的监听，以避免出现内存泄漏问题。

除了事件总线外，Vue还提供了其他多种组件通信的方式，如父子组件之间的props传递、自定义事件系统等，根据具体需求选择适合的方式来实现组件间的通信。

![[attachments/Untitled 6 6.png|Untitled 6 6.png]]

  

![[attachments/Untitled 7 6.png|Untitled 7 6.png]]

![[attachments/Untitled 8 6.png|Untitled 8 6.png]]

![[attachments/Untitled 9 6.png|Untitled 9 6.png]]

![[attachments/Untitled 10 6.png|Untitled 10 6.png]]

![[attachments/Untitled 11 5.png|Untitled 11 5.png]]

事件总线

![[attachments/Untitled 12 5.png|Untitled 12 5.png]]

### 5.组件中的v-model和sync

![[attachments/Untitled 13 5.png|Untitled 13 5.png]]

![[attachments/Untitled 14 5.png|Untitled 14 5.png]]

![[attachments/Untitled 15 5.png|Untitled 15 5.png]]

![[attachments/Untitled 16 5.png|Untitled 16 5.png]]

sync

  

![[attachments/Untitled 17 5.png|Untitled 17 5.png]]

  

### 6.ref和$ref $nextTikt

![[attachments/Untitled 18 5.png|Untitled 18 5.png]]

  

![[attachments/Untitled 19 5.png|Untitled 19 5.png]]

  

![[attachments/Untitled 20 5.png|Untitled 20 5.png]]

  

![[attachments/Untitled 21 5.png|Untitled 21 5.png]]

  

![[attachments/Untitled 22 5.png|Untitled 22 5.png]]

### 7.自定义指令

![[attachments/Untitled 23 5.png|Untitled 23 5.png]]

  

![[attachments/Untitled 24 5.png|Untitled 24 5.png]]

  

![[attachments/Untitled 25 5.png|Untitled 25 5.png]]

  

![[attachments/Untitled 26 5.png|Untitled 26 5.png]]

### 8.插槽

后备内容（默认插槽）

![[attachments/Untitled 27 5.png|Untitled 27 5.png]]

具名插槽 v-slot：name

![[attachments/Untitled 28 5.png|Untitled 28 5.png]]

作用域插槽

![[attachments/Untitled 29 5.png|Untitled 29 5.png]]

  

### 9.路由

  

![[attachments/Untitled 30 5.png|Untitled 30 5.png]]

  

![[attachments/Untitled 31 5.png|Untitled 31 5.png]]

  

![[attachments/Untitled 32 5.png|Untitled 32 5.png]]

  

![[attachments/Untitled 33 5.png|Untitled 33 5.png]]

  

![[attachments/Untitled 34 5.png|Untitled 34 5.png]]

  

![[attachments/Untitled 35 5.png|Untitled 35 5.png]]

  

![[attachments/Untitled 36 4.png|Untitled 36 4.png]]

  

![[attachments/Untitled 37 4.png|Untitled 37 4.png]]

![[attachments/Untitled 38 4.png|Untitled 38 4.png]]

  

### 10.路由进阶

  

![[attachments/Untitled 39 4.png|Untitled 39 4.png]]

  

![[attachments/Untitled 40 4.png|Untitled 40 4.png]]

  

![[attachments/Untitled 41 4.png|Untitled 41 4.png]]

  

![[attachments/Untitled 42 4.png|Untitled 42 4.png]]

  

路由传参

![[attachments/Untitled 43 4.png|Untitled 43 4.png]]

  

![[attachments/Untitled 44 4.png|Untitled 44 4.png]]

  

![[attachments/Untitled 45 4.png|Untitled 45 4.png]]

  

![[attachments/Untitled 46 4.png|Untitled 46 4.png]]

  

![[attachments/Untitled 47 4.png|Untitled 47 4.png]]

  

![[attachments/Untitled 48 4.png|Untitled 48 4.png]]

  

![[attachments/Untitled 49 4.png|Untitled 49 4.png]]

  

![[attachments/Untitled 50 4.png|Untitled 50 4.png]]

  

![[attachments/Untitled 51 4.png|Untitled 51 4.png]]

  

  

![[attachments/Untitled 52 4.png|Untitled 52 4.png]]

  

![[attachments/Untitled 53 4.png|Untitled 53 4.png]]

  

![[attachments/Untitled 54 4.png|Untitled 54 4.png]]

  

![[attachments/Untitled 55 4.png|Untitled 55 4.png]]

  

![[attachments/Untitled 56 4.png|Untitled 56 4.png]]

  

![[attachments/Untitled 57 4.png|Untitled 57 4.png]]
  

  

### 路由缓存

  

  

![[attachments/Untitled 77.png|Untitled 77.png]]

  

![[attachments/Untitled 1 4.png|Untitled 1 4.png]]

  

![[attachments/Untitled 2 5.png|Untitled 2 5.png]]

  

![[attachments/Untitled 3 5.png|Untitled 3 5.png]]

  

### 路由滚动行为

  

![[attachments/Untitled 4 5.png|Untitled 4 5.png]]

  

  

### key

  

![[attachments/Untitled 5 4.png|Untitled 5 4.png]]

  

  

### Hooks

  

![[attachments/Untitled 6 4.png|Untitled 6 4.png]]

![[attachments/Untitled 7 4.png|Untitled 7 4.png]]

  

### 模版渲染多层属性访问

![[attachments/Untitled 8 4.png|Untitled 8 4.png]]

### SKU组件

  

![[attachments/Untitled 9 4.png|Untitled 9 4.png]]

  

  

### try catch finall

  

  

![[attachments/Untitled 10 4.png|Untitled 10 4.png]]

  

  

  

  

Vue 事件绑定

在原生 js 中只能传递函数名来进行事件绑定，但 vue 可以传入带参数的函数 ，vue 是如何实现的

  

在 Vue 中，事件绑定并不是直接传递函数名，而是传递一个 JavaScript 表达式。当你在模板中使用 `v-on` 指令时，你可以传递一个 JavaScript 表达式，这个表达式可以是一个函数调用，也可以是一个函数本身。这个表达式会在触发事件时求值并执行。  
因此，Vue 是通过在事件触发时动态地评估表达式来实现传递带参数的函数的。Vue 在内部使用了事件代理，它将事件监听器附加到实际的 DOM 元素上，并在事件触发时调用指定的 JavaScript 表达式。这样就可以轻松地传递参数给事件处理函数，而不仅限于传递函数名。  

  

两者的本质区别是什么

  

在原生 JavaScript 中，事件绑定只能通过指定函数名的方式，事件触发时会调用该函数。这意味着在绑定事件时无法直接传递参数给函数，需要通过闭包或其他手段来实现参数传递。  
而在 Vue 中，事件绑定不仅可以通过指定函数名，还可以传递一个 JavaScript 表达式，该表达式在事件触发时会被动态求值并执行。这使得在绑定事件时能够直接传递参数给函数，使得代码更加简洁和灵活。Vue 内部通过事件代理来实现这一机制，以便在事件触发时调用指定的 JavaScript 表达式，从而达到传递参数的目的。因此，Vue 提供了更加方便和灵活的事件处理机制，与原生 JavaScript 相比，更易于开发和维护。
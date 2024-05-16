![[Pasted image 20240407172405.png]]
面试题:请闻述vue的diff算法
参考回答
当组件创建和更新时，vue均会执行内部的update函数，该函数在内部调用render函数生成虚拟dom树，组
件会指向新树，然后vue将新旧两树进行对比，找到差异点，最终更新到真实dom
对比差异的过程叫diff，vue在内部通过一个叫patch的函数完成该过程
在对比时，vue采用深度优先、逐层比较的方式进行比对。
在判断两个节点是否相同时，vue是通过虚拟节点的key和tag来进行判断的
具体来说，首先对根节点进行对比，如果相同则将旧节点关联的真实dom的引用挂到新节点上，然后根据需
要更新属性到真实dom，然后再对比其子节点数组;如果不相同，则按照新节点的信息递归创建所有真实
dom，同时挂到对应虚拟节点上，然后移除掉旧的dom。
在对比其子节点数组时，vue对每个子节点数组使用了两个指针，分别指向头尾，然后不断向中间靠拢来进行
对比，这样做的目的是尽量复用真实dom，尽量少的销毁和创建真实dom。如果发现相同，则进入和根节点
一样的对比流程，如果发现不同，则移动真实dom到合适的位置。
这样一直递归的遍历下去，直到整棵树完成对比。



得分点 patch、patchVnode、updateChildren、vue优化时间复杂度为O(n) 

标准回答
Diff算法比较过程 、
第一步：patch函数中对新老节点进行比较 如果新节点不存在就销毁老节点 如果老节点不存在，直接创建新的节点 当两个节点是相同节点的时候，进入 patctVnode 的过程，比较两个节点的内部 
第二步：patchVnode函数比较两个虚拟节点内部 如果两个虚拟节点完全相同，返回 当前vnode 的children 不是textNode，再分成三种情况 - 有新children，没有旧children，创建新的 - 没有新children，有旧children，删除旧的 - 新children、旧children都有，执行`updateChildren`比较children的差异，这里就是diff算法的核心 当前vnode 的children 是textNode，直接更新text 
第三步：updateChildren函数子节点进行比较 
- 第一步 头头比较。若相似，旧头新头指针后移（即 `oldStartIdx++` && `newStartIdx++`），真实dom不变，进入下一次循环；不相似，进入第二步。 
- - 第二步 尾尾比较。若相似，旧尾新尾指针前移（即 `oldEndIdx--` && `newEndIdx--`），真实dom不变，进入下一次循环；不相似，进入第三步。 
- - 第三步 头尾比较。若相似，旧头指针后移，新尾指针前移（即 `oldStartIdx++` && `newEndIdx--`），未确认dom序列中的头移到尾，进入下一次循环；不相似，进入第四步。 
- - 第四步 尾头比较。若相似，旧尾指针前移，新头指针后移（即 `oldEndIdx--` && `newStartIdx++`），未确认dom序列中的尾移到头，进入下一次循环；不相似，进入第五步。
-  - 第五步 若节点有key且在旧子节点数组中找到sameVnode（tag和key都一致），则将其dom移动到当前真实dom序列的头部，新头指针后移（即 `newStartIdx++`）；否则，vnode对应的dom（`vnode[newStartIdx].elm`）插入当前真实dom序列的头部，新头指针后移（即 `newStartIdx++`）。 
- - 但结束循环后，有两种情况需要考虑： 
- - 新的字节点数组（newCh）被遍历完（`newStartIdx > newEndIdx`）。那就需要把多余的旧dom（`oldStartIdx -> oldEndIdx`）都删除，上述例子中就是`c,d`； - 新的字节点数组（oldCh）被遍历完（`oldStartIdx > oldEndIdx`）。那就需要把多余的新dom（`newStartIdx -> newEndIdx`）都添加。



自己总结

当我们当前组件所依赖的数值更新和组件创建时运行update函数，update函数会调用组件的render函数，render生成新的虚拟dom树，update函数内部传入render函数生成的新的虚拟DOM树
然后在update函数中 先把之前的旧虚拟DOM树存入oldVNode变量中 把传入的新的虚拟DOM树赋值给\_vnode
之后对新旧vnode的对比，

#### patch 函数
上面我们说了，patch是比较的开始，相当于是diff的入口，diff就是从这一步开始的。那么既然是开始，说明patch函数比较的肯定就是两个新旧vdom的根节点了。所以，两个vdom直接的比较，patch是只会触发一次的。



#### patchVnode

patchVnode 是用于比较两个相同节点的子级（文本，或子节点）的一个函数。故它的调用总是在sameVnode判断之后。只有判断当前比较的两个vnode相同时（这里我最后再解释一次，两个vnode相同仅仅代表key相同且sel选择器相同），才会被执行。  
但，在比对之前，会先判断下oldVnode === vNode ，因为如果全等，代表子级肯定也完全相等，那么就没必要对比了，直接return;  
作用：对比新旧两个节点，更新dom的子级（子级包含文本或者是子节点）  
对比过程：
1、如果存在属性（data）
- 更新属性

2、如果新vnode有text节点
- 旧vnode是否有子节点，如果有，代表原来是子节点，现在变成文本了，那么删除子节点，并且设置vnode对象的真实dom的text值（使用setTextContent函数）
- 其他情况不用管，直接设置vnode对象的真实dom的text值  

3、如果新vnode没有text节点
- 如果新vnode和旧vnode都存在子节点时。是不是要深度对比两个vnode的子节点啊。这个时候会进入第三步，比较子节点（执行updateChildren）  
- 如果只有新vnode有子节点，老vnode没有，那么很简单，执行添加节点的操作  
- 如果只有旧vnode有子节点，新vnode没有子节点，很明显，要执行删除旧vnode子节点的操作  

2、patch比较如果相同，对两个节点执行patchVnode（oldVnode, newVnode）patchVnode 是用于比较两个相同节点的子级（文本，或子节点）的一个函数。故它的调用总是在sameVnode判断之后。只有判断当前比较的两个vnode相同时，才会被执行。
两个节点的属性是否相同，节点是否存在文本，文本是否相同。是否存在子节点，子节点是否相同。此时
- 新节点的属性是否变化，如果是则更新属性  
- 新节点是否存在文本节点，如果是，则直接更新`dom`的文本内容为新节点的文本内容
- 新节点和旧节点如果都有子节点，则处理比较更新子节点，那么会进入updateChildren来比较子节点的差异。
- 只有新节点有子节点，旧节点没有，那么不用比较了，所有节点都是全新的，所以直接全部新建就好了，新建是指创建出所有新`DOM`，并且添加进父节点
- 只有旧节点有子节点而新节点没有，说明更新后的页面，旧节点全部都不见了，那么要做的，就是把所有的旧节点删除，也就是直接把`DOM` 删除

1、如果存在文本节点时，更新文本  
2、如果存在属性时，更新属性  
3、如果存在子节点时，更新子节点  
那么，如何更新呢，逻辑也很简单，遵循以下规则：  
1、如果旧vnode上存在，而新vnode上不存在，那么执行删除操作  
2、如果旧vnode上不存在，而新vnode上存在，那么执行新增操作  
3、如果新旧vnode上都存在，那么执行替换操作（即，新增新的，删除旧的），文本，和属性的替换是在这部分完成。而对于子节点，如果新vnode和旧vnode上都存在子节点时，那么会进入updateChildren来比较子节点的差异。

3、updateChildren函数子节点进行比较 
- 第一步 头头比较。若相似，旧头新头指针后移（即 `oldStartIdx++` && `newStartIdx++`），真实dom不变，进入下一次循环；不相似，进入第二步。 
- - 第二步 尾尾比较。若相似，旧尾新尾指针前移（即 `oldEndIdx--` && `newEndIdx--`），真实dom不变，进入下一次循环；不相似，进入第三步。 
- - 第三步 头尾比较。若相似，旧头指针后移，新尾指针前移（即 `oldStartIdx++` && `newEndIdx--`），未确认dom序列中的头移到尾，进入下一次循环；不相似，进入第四步。 
- - 第四步 尾头比较。若相似，旧尾指针前移，新头指针后移（即 `oldEndIdx--` && `newStartIdx++`），未确认dom序列中的尾移到头，进入下一次循环；不相似，进入第五步。
-  - 第五步 若节点有key且在旧子节点数组中找到sameVnode（tag和key都一致），则将其dom移动到当前真实dom序列的头部，新头指针后移（即 `newStartIdx++`）；否则，vnode对应的dom（`vnode[newStartIdx].elm`）插入当前真实dom序列的头部，新头指针后移（即 `newStartIdx++`）。 
- - 但结束循环后，有两种情况需要考虑： 
- - 新的字节点数组（newCh）被遍历完（`newStartIdx > newEndIdx`）。那就需要把多余的旧dom（`oldStartIdx -> oldEndIdx`）都删除，上述例子中就是`c,d`； - 新的字节点数组（oldCh）被遍历完（`oldStartIdx > oldEndIdx`）。那就需要把多余的新dom（`newStartIdx -> newEndIdx`）都添加。
3、比较分3大类。  
第一类：oldStart === newStart， oldStart === newEnd，oldEnd === newStart，oldEnd === newEnd 这4种情况的比较。如果这4种情况中任何一种匹配。那么会执行patchVnode进一步比较。同时指针往中间移

第二类：oldStart > oldEnd 或者 newStart > newEnd时。表示匹配结束。此时，多余的元素删除，新增的元素新增。

第三类：上面几种情况都不匹配。那么这个时候key是否存在。就起到关键性作用了。存在key时，可以直接通过key去找到节点的原来的位置。如果没有找到，就新增节点。找到了，就移动节点位置。查找效率非常高  
而如果没有key呢，那么压根就不会去原来的节点中查找了。而是直接新增这个节点。这就导致这个节点下的所有子节点都会被重新新增。会出现明显的性能损耗。所以，合理的应用key，也是一种性能上的优化。
总之一句话。diff的过程，就是一个 patch —> patchVnode —> updateChildren —> patchVnode —> updateChildren —> patchVnode… 这样的一个循环递归的过程






2patch比较如果相同，对两个节点执行patchVnode（oldVnode, newVnode），比较两个节点的属性是否相同，节点是否存在文本，文本是否相同。是否存在子节点，子节点是否相同。
- 新节点是否存在文本节点，如果是，则直接更新`dom`的文本内容为新节点的文本内容
- 新节点和旧节点如果都有子节点，则处理比较更新子节点
- 只有新节点有子节点，旧节点没有，那么不用比较了，所有节点都是全新的，所以直接全部新建就好了，新建是指创建出所有新`DOM`，并且添加进父节点
- 只有旧节点有子节点而新节点没有，说明更新后的页面，旧节点全部都不见了，那么要做的，就是把所有的旧节点删除，也就是直接把`DOM` 删除



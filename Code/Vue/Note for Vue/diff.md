组件绑定数据更新是 组件创建时 运行updata函数 内部参数是render函数返回的新的vnode
在 update 函数中会先讲旧的vnode存入oldVNode变量 然后将——vnode重新负值为新的闯入的vnode
然后运行patch函数对新旧vnode的根节点进行比较
patch函数会判断两只是否为sameVNode是则进入patchVNode函数
不是 则 如果没有newVnode 则直接销毁旧节点
 如果 没有老节点 则是初始化阶段 之间创建新节点
如果节点都存在但是不同则直接创新的 销毁旧的


接下来是patchVnode函数
patchvnode函数会判断两者是否在同一内存空间===
如果是则直接返回退出

如果有属性则更新属性
如果是new  是 text节点 
老节点有子节点 销毁老的 创建新的
如果都是text节点 则更新文本内容


new 不是text节点  证明是new有子节点


如果old是文本节点则把文本内容删除，然后全部新建节点
如果没有newVnode进行删除操作
如果都有子节点进入 updateChilrden


updateChilrden 

将新老vnode子节点数组进行diff算法比较
比较流程
循环判断
条件是 oldstart <= oldend  &&
newstart <= newend


先进行 new头 old头比较 若相似 两节点进行patchVNode  两个头索引+1 然后进入下一次循环 不相似继续判断
进行 new尾 old 尾比较  若相似   两节 点进行patchVNode  两个尾索引-1 然后进入下一次循环 不相似继续判断
new尾 和 old头 比较 相似 把两节 点进行patchVNode 然后把当前真实dom节点移动到 oldEND后面 new尾-1  old头+1
new头 和 old尾 比较 相似 把两节 点进行patchVNode 然后把当前真实dom节点移动到 oldstart前面 old尾-1  new头+1

如果都不行  若有key   看在oldVnode子节点数组中能否找到sameVNode 找到了则把真实dom节点移动到 oldStart前面 


若没有key或者找不到则新建节点到真实dom队列头部



如果while循环退出则若是new部分先遍历完成 old还剩子节点 则直接进行删除
若是old部分先遍历完成 new还剩子节点 则直接进行在oldstartinde前面新增 
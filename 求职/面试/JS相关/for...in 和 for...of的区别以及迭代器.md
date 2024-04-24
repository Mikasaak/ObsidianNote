### for...in 和 for...of的区别
for...in是遍历可枚举属性 可以遍历object会遍历到原型链上不属于自己本身的属性
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

for...of是遍历可迭代对象
**`for...of`** 语句执行一个循环，该循环处理来自[可迭代对象](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E5%8F%AF%E8%BF%AD%E4%BB%A3%E5%8D%8F%E8%AE%AE)的值序列。可迭代对象包括内置对象的实例，例如 [`Array`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array)、[`String`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String)、[`TypedArray`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/TypedArray)、[`Map`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Map)、[`Set`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Set)、[`NodeList`](https://developer.mozilla.org/zh-CN/docs/Web/API/NodeList)（以及其他 DOM 集合），还包括 [`arguments`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Functions/arguments) 对象、由[生成器函数](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/function*)生成的[生成器](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Generator)，以及用户定义的可迭代对象。

#### [描述](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/for...of#%E6%8F%8F%E8%BF%B0)

`for...of` 循环按顺序逐个处理从可迭代对象获取的值。循环对值的每次操作被称为一次_迭代_，而循环本身被称为_迭代可迭代对象_。每次迭代都会执行可能引用当前序列值的语句。

当 `for...of` 循环迭代一个可迭代对象时，它首先调用可迭代对象的 [`[@@iterator]()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Symbol/iterator) 方法，该方法返回一个[迭代器](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E8%BF%AD%E4%BB%A3%E5%99%A8%E5%8D%8F%E8%AE%AE)，然后重复调用生成器的 [`next()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E8%BF%AD%E4%BB%A3%E5%99%A8%E5%8D%8F%E8%AE%AE) 方法，以生成要分配给 `variable` 的值的序列。

`for...of` 循环在迭代器完成时退出（即迭代器的 `next()` 方法返回一个包含 `done: true` 的对象）。你也可以使用控制流语句来改变正常的控制流程。[`break`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/break) 语句退出循环并跳转到循环体后的第一条语句，而 [`continue`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/continue) 语句跳过当前迭代的剩余语句，继续进行下一次迭代。

如果 `for...of` 循环提前退出（例如遇到 `break` 语句或抛出错误），则会调用迭代器的 [`return()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E8%BF%AD%E4%BB%A3%E5%99%A8%E5%8D%8F%E8%AE%AE) 方法来执行任何清理任务。

`for...of` 的 `variable` 部分可以接受任何在 = 运算符之前的内容。只要在循环体内部不重新赋值（可以在迭代之间更改，因为它们是两个独立的变量），你可以使用 [`const`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/const) 来声明变量。否则，你可以使用 [`let`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/let)。

### 迭代协议

**迭代协议**并不是新的内置实现或语法，而是_协议_。这些协议可以被任何遵循某些约定的对象来实现。

迭代协议具体分为两个协议：[可迭代协议](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E5%8F%AF%E8%BF%AD%E4%BB%A3%E5%8D%8F%E8%AE%AE)和[迭代器协议](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E8%BF%AD%E4%BB%A3%E5%99%A8%E5%8D%8F%E8%AE%AE)。

##### [可迭代协议](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E5%8F%AF%E8%BF%AD%E4%BB%A3%E5%8D%8F%E8%AE%AE)

**可迭代协议**允许 JavaScript 对象定义或定制它们的迭代行为，例如，在一个 [`for..of`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/for...of) 结构中，哪些值可以被遍历到。一些内置类型同时是[内置的可迭代对象](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E5%86%85%E7%BD%AE%E7%9A%84%E5%8F%AF%E8%BF%AD%E4%BB%A3%E5%AF%B9%E8%B1%A1)，并且有默认的迭代行为，比如 [`Array`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array) 或者 [`Map`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Map)，而其他内置类型则不是（比如 [`Object`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object)）。

要成为**可迭代**对象，该对象必须实现 **`@@iterator`** 方法，这意味着对象（或者它[原型链](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)上的某个对象）必须有一个键为 `@@iterator` 的属性，可通过常量 [`Symbol.iterator`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Symbol/iterator) 访问该属性：

[`[Symbol.iterator]`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#symbol.iterator)

一个无参数的函数，其返回值为一个符合[迭代器协议](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E8%BF%AD%E4%BB%A3%E5%99%A8%E5%8D%8F%E8%AE%AE)的对象。

当一个对象需要被迭代的时候（比如被置入一个 [`for...of`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/for...of) 循环时），首先，会不带参数调用它的 `@@iterator` 方法，然后使用此方法返回的**迭代器**获得要迭代的值。

值得注意的是调用此无参数函数时，它将作为对可迭代对象的方法进行调用。因此，在函数内部，`this` 关键字可用于访问可迭代对象的属性，以决定在迭代过程中提供什么。

此函数可以是普通函数，也可以是生成器函数，以便在调用时返回迭代器对象。在此生成器函数的内部，可以使用 `yield` 提供每个条目。

##### [迭代器协议](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E8%BF%AD%E4%BB%A3%E5%99%A8%E5%8D%8F%E8%AE%AE)

**迭代器协议**定义了产生一系列值（无论是有限个还是无限个）的标准方式，当值为有限个时，所有的值都被迭代完毕后，则会返回一个默认返回值。

只有实现了一个拥有以下语义（semantic）的 **`next()`** 方法，一个对象才能成为迭代器：

[`next()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#next)

无参数或者接受一个参数的函数，并返回符合 `IteratorResult` 接口的对象（见下文）。如果在使用迭代器内置的语言特征（例如 `for...of`）时，得到一个非对象返回值（例如 `false` 或 `undefined`），将会抛出 [`TypeError`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/TypeError)（`"iterator.next() returned a non-object value"`）。

所有迭代器协议的方法（`next()`、`return()` 和 `throw()`）都应返回实现 `IteratorResult` 接口的对象。它必须有以下属性：

[`done`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#done) 可选

如果迭代器能够生成序列中的下一个值，则返回 `false` 布尔值。（这等价于没有指定 `done` 这个属性。）

如果迭代器已将序列迭代完毕，则为 `true`。这种情况下，`value` 是可选的，如果它依然存在，即为迭代结束之后的默认返回值。

[`value`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#value) 可选

迭代器返回的任何 JavaScript 值。`done` 为 `true` 时可省略。

实际上，两者都不是严格要求的；如果返回没有任何属性的对象，则实际上等价于 `{ done: false, value: undefined }`。

如果一个迭代器返回一个 `done: true` 的结果，则对任何 `next()` 的后续调用也返回 `done: true`，尽管这在语言层面不是强制的。

`next` 方法可以接受一个值，该值将提供给方法体。任何内置的语言特征都将不会传递任何值。传递给[生成器](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Generator) `next` 方法的值将成为相应 `yield` 表达式的值。

可选地，迭代器也实现了 **`return(value)`** 和 **`throw(exception)`** 方法，这些方法在调用时告诉迭代器，调用者已经完成迭代，并且可以执行任何必要的清理（例如关闭数据库连接）。

[`return(value)`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#returnvalue) 可选

无参数或者接受一个参数的函数，并返回符合 `IteratorResult` 接口的对象，其 `value` 通常等价于传递的 `value`，并且 `done` 等于 `true`。调用这个方法表明迭代器的调用者不打算调用更多的 `next()`，并且可以进行清理工作。

[`throw(exception)`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#throwexception) 可选

无参数或者接受一个参数的函数，并返回符合 `IteratorResult` 接口的对象，通常 `done` 等于 `true`。调用这个方法表明迭代器的调用者监测到错误的状况，并且 `exception` 通常是一个 [`Error`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Error) 实例。

**备注：** 无法通过反射的方法确定（例如，没有实际调用 `next()` 并验证返回的结果）一个特定的对象是否实现了迭代器协议。

很容易使一个迭代器也可迭代：只需实现 `[@@iterator]()` 方法，并返回它的 `this`。


```js
// Satisfies both the Iterator Protocol and Iterable
const myIterator = {
  next() {
    // ...
  },
  [Symbol.iterator]() {
    return this;
  },
};
```

这种对象被称为_可迭代迭代器_。这样做可以让期望可迭代对象的各类语法使用此类迭代器——因此，在不实现可迭代协议的情况下，仅实现迭代器协议的作用很小。（事实上，几乎所有的语法和 API 都期待_可迭代对象，而不是迭代器_。）[生成器对象](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Generator)是一个例子：


```js
const aGeneratorObject = (function* () {
  yield 1;
  yield 2;
  yield 3;
})();

console.log(typeof aGeneratorObject.next);
// "function"——它有 next 方法（返回正确的值），所以它是迭代器

console.log(typeof aGeneratorObject[Symbol.iterator]);
// "function"——它有 @@iterator 方法（返回正确的迭代器），所以它是可迭代的

console.log(aGeneratorObject[Symbol.iterator]() === aGeneratorObject);
// true——它的 @@iterator 方法返回自身（一个迭代器），所以它是一个可迭代的迭代器
```

然而，可能的情况下，`iterable[Symbol.iterator]` 最好返回总是从头开始的不同的迭代器，像 [`Set.prototype[@@iterator]()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Set/@@iterator) 做的那样。

### 迭代器和生成器
#### 迭代器：
一个键值为Symbol.iterator的方法；其返回一个有next方法的对象；next方法返回一个具有done，value属性的对象
**`Iterator`** 对象是一个符合[迭代器协议](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E8%BF%AD%E4%BB%A3%E5%99%A8%E5%8D%8F%E8%AE%AE)的对象，其提供了 `next()` 方法用以返回迭代器结果对象。所有内置迭代器都继承自 `Iterator` 类。`Iterator` 类提供了 [`@@iterator`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Iterator/@@iterator) 方法，该方法返回迭代器对象本身，使迭代器也[可迭代](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E5%8F%AF%E8%BF%AD%E4%BB%A3%E5%8D%8F%E8%AE%AE)。它还提供了一些使用迭代器的辅助方法。
#### 生成器：
**`Generator`** 对象由[生成器函数](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/function*)返回并且它符合[可迭代协议](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E5%8F%AF%E8%BF%AD%E4%BB%A3%E5%8D%8F%E8%AE%AE)和[迭代器协议](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols#%E8%BF%AD%E4%BB%A3%E5%99%A8%E5%8D%8F%E8%AE%AE)。

#### 代码
```js
//手写迭代器
let obj = {
  a: 1,
  b: 2,
  c: 3,
  [Symbol.iterator]: function () {
    let keys = Object.keys(this);
    let index = 0;
    return {
      next: () => {
        return {
          value: this[keys[index++]],
          done: index > keys.length
        }
      }
    }
  }
}
//生成器函数生成迭代器协议
let obj2 = {
  a: 's',
  b: 'a',
  c: 'k',
  d: 'a',
  [Symbol.iterator]: function* () {
    let keys = Object.keys(this);
    for (let key of keys) {
      yield this[key];
    }
  }
}
for (let value of obj) {
  console.log(value);
}
for (let value of obj2) {
  console.log(value);
}
```
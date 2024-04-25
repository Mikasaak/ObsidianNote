JavaScript 的数组排序是一个非常常见业务场景，ECMAScript 为数组提供了一个原生的sort函数，今天我们就来好好看看你对sort函数究竟了解多少。

## 首先我们来看一下`sort`函数的基本信息

```js
语法：
arr.sort([compareFunction])
参数:
compareFunction [可选]
用于数组排序规则的比较函数。如果不含有该参数，数组元素按照转换字符串的各个字符的Unicode编码顺序进行排序。
    compareFunction 参数：
    firstElement   用于比较的第一个元素
    secondElement  用于比较的第二个元素
返回值:
排序后的数组，返回的是当前数组。
```

我们先来看看各种排序的应用方式

## **没有参数的默认排序**

```js
// 当没有参数传入时 默认按照数组转成字符串后的结果每一位的Unicode编码进行排序
let arr = [311,43,54,4,40,26,31,33];
arr.sort();
console.log(arr); // [26, 31, 311, 33, 4, 40, 43, 54]
```

## **升序排列**

```js
let arr = [311,43,54,4,40,26,31,33];
arr.sort((a,b) => b - a);
console.log(arr); // [311, 54, 43, 40, 33, 31, 26, 4]
```

好了，看完升序和降序排列以后我们来聊聊排序的规则。

如果添加了 compareFunction 那么数组会按该函数的返回值结果进行排序,即 compareFunction(a,b) 表示 a,b的比较结果，规则如下：

- 如果返回值结果小于0，则a和b的顺序不变;
- 如果返回值结果等于0，则a和b的顺序不变;
- 如果返回值的结果大于0，a和b会交换位置。

了解了以上排序结果以后我们可以使用sort方法颠倒数组的顺序(实现类似于reverse方法的效果)

```js
let arr = [311,43,54,4,40,26,31,33];
arr.sort(() => -1);
console.log(arr); // [33, 31, 26, 40, 4, 54, 43, 311]
```

## 随机排序

```js
let arr = [311,43,54,4,40,26,31,33];
arr.sort((a,b) => Math.random() - 0.5);
console.log(arr); // 结果为随机排序
```

## **按照对象指定的属性值进行升序或降序排列**

```js
var arr = [{
    name: 'zhangsan',
    age: 20
}, {
    name: 'lisi',
    age: 15
}, {
    name: 'wangwu',
    age: 17
}, {
    name: 'zhaoliu',
    age: 23
}, {
    name: 'fengqi',
    age: 31
}, {
    name: 'xiaoming',
    age: 11
}];


function sortby(prop, rev = true) {
     // prop 属性名
     // rev  升序降序 默认升序
      return function(a, b) {
         var val1 = a[prop]; 
         var val2 = b[prop]; 
         return rev ? val1 - val2 : val2 - val1;
      }
}

arr.sort(sortby('age')); // 根据age进行升序排列
arr.sort(sortby('age',false)); // 根据age进行降序排列
```

**升序排列结果 :**

![](https://pic1.zhimg.com/v2-2e22e9a768efc1e663e70de786e0eedc_r.jpg)

**降序排列结果 :**

![](https://pic1.zhimg.com/v2-13a81ed9721221b727084f6ed0b2fbd8_r.jpg)

我们再来看一个特别的排序方式

## **先按奇数升序排列，后按偶数升序排列**

```js
let arr = [311,43,54,4,40,26,31,33];
arr.sort((a,b)=>{
    if(!(a % 2) && b % 2) return 1; // 首先满足条件a为偶数,b为奇数
    if((a % 2 && b % 2 || !(a % 2) && !(b % 2)) && a > b) return 1; // 判断a b 均为奇数或偶数 且a > b 即可进行升序排序
    return -1;
});
console.log(arr); // [31, 33, 43, 311, 4, 26, 40, 54]
```

[2020版Web前端_HTML5教程_完全入门_学完达到前端工程师水平_哔哩哔哩 (゜-゜)つロ 干杯~-bilibili​www.bilibili.com/video/BV1r64y1T7J8?ssss![](https://pic2.zhimg.com/v2-a67017acd9f2fcb78cf2aa4548814485_180x120.jpg)](https://www.bilibili.com/video/BV1r64y1T7J8?ssss)

[JavaScript正则表达式的使用+歌词滚动案例_哔哩哔哩 (゜-゜)つロ 干杯~-bilibili​www.bilibili.com/video/BV1eK4y1j793?ssss![](https://pic1.zhimg.com/v2-f8e487e67f4d8634be97d3e71adefd1c_180x120.jpg)](https://www.bilibili.com/video/BV1eK4y1j793?ssss)

[JavaScript DOM的概念及基本操作_哔哩哔哩 (゜-゜)つロ 干杯~-bilibili​www.bilibili.com/video/BV14r4y1w751?ssss![](https://pic2.zhimg.com/v2-99028b11b4348d0af90c20630390419d_180x120.jpg)](https://www.bilibili.com/video/BV14r4y1w751?ssss)

原文来自知乎：千锋HTML5学院

原文链接：[被玩坏的数组排序之sort函数](https://zhuanlan.zhihu.com/p/334336665)
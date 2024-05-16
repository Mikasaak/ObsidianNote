---
description: 
pubDate:
tags: 
title: a标签如何禁止href跳转或链接？
date_created: 2024-05-14日 星期二 , 04:11:19 下午
date_modified: 2024-05-14日 星期二 , 04:16:22 下午
---
在做页面时，如果想做一个链接点击后不做任何事情，或者响应点击而完成其他事情，可以设置其属性 href = "#"，但是，这样会有一个问题，就是当页面有滚动条时，点击后会返回到页面顶端，用户体验不好。

## （1）阻止默认事件

> 阻止默认事件的发生有两个方法：
> 
> - return false
> - e.preventDefault()


```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title></title>
    </head>
    <body>
        <a href="https://www.baidu.com/">去百度</a><br>
        <!-- 阻止默认事件两种方法 -->
        <a href="https://www.baidu.com/" onclick="return false">去百度(禁止默认事件:return false)</a><br>
        <a href="https://www.baidu.com/" id="go">去百度(禁止默认事件:e.preventDefault())</a>
        <script>
            //获取元素节点 
            let go = document.querySelector("#go")
            // 点击事件
            go.onclick = function (e) {
                // 阻止默认事件
                e.preventDefault()
            }
        </script>
    </body>
</html>
```

通过阻止a标签默认事件就可以禁止a标签跳转！


## （2）javascript:void(0)（少用）

javascript:void(0)这是一种伪协议，void(0)在IE中可能会引起一些问题，比如：造成gif动画停止播放等

void是javascipt自身的操作符，它表示的是只执行表达式，但没有返回值！
```html
<a href="javascript:void(0)">点击无法跳转(javascript:void(0))</a>
<a href="javascript:void(null)">点击无法跳转(javascript:void(null))</a>
```

这两种写法都可以，都表示一个死链接，点击无效果


## （3）javascript:;

javascript:; 执行一段空白的javascript语句，返回空或者false值，从而防止链接跳转

javascript:; 写法比 javascript:void(0) 好，后者存在浏览器兼容bug

```html
<a href="javascript:;">点击无法跳转(javascript:;)</a>
```

## （4）href(####)

> 使用2个到4个#，见的大多是"####"，也有使用"#all"等其他的。一个无意义的标签指定，不做任何处理。
> 
> （这种方法会在浏览器地址栏上出现“####”）

```html
<a href="####">点击无法跳转</a>
```

注意：只是用一个“#”是不行的，会默认刷新页面回到页面顶部


**总结：**

- `<a href="####"></a>  `
    
- `<a href="javascript:void(0)"></a>  `
    
- `<a href="javascript:void(null)"></a>`  
    
- `<a href="#" onclick="return false"></a>`  
    
- `<a href="#" id="go"></a>`

```html
<script>
    let go = document.querySelector("#go")
    go.onclick = function (e) {
        e.preventDefault()
    }
</script>
```

本文来自博客园，作者：[不知名前端李小白](https://www.cnblogs.com/libo-web/)，转载请注明原文链接：[https://www.cnblogs.com/libo-web/p/15798017.html](https://www.cnblogs.com/libo-web/p/15798017.html)
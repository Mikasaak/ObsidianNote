---
description: 
pubDate:
tags: 
title: CSS样式的优先级（选择器的权重）问题
date_created: 2024-05-6日 星期一 , 10:32:15 上午
date_modified: 2024-05-6日 星期一 , 10:33:00 上午
---
# CSS样式的优先级（选择器的权重）问题

#### 文章目录

- - [一. CSS权重](https://blog.csdn.net/JZevin/article/details/109367058#_CSS_1)
    - [二. 优先级分类](https://blog.csdn.net/JZevin/article/details/109367058#__4)
    - [三. 优先规则](https://blog.csdn.net/JZevin/article/details/109367058#__14)
    - [四. 实例解析](https://blog.csdn.net/JZevin/article/details/109367058#__23)
    - - [4.1 实例一](https://blog.csdn.net/JZevin/article/details/109367058#41__25)
        - [4.2 实例二](https://blog.csdn.net/JZevin/article/details/109367058#42__37)

### 一. CSS权重

CSS权重指的是样式的优先级，当同一个元素出现样式冲突时，会比较[选择器](https://so.csdn.net/so/search?q=%E9%80%89%E6%8B%A9%E5%99%A8&spm=1001.2101.3001.7020)之间的权重来决定谁生效。具体的选择器权重如下：

### 二. 优先级分类

|优先级|选择器 / 样式|权重值|备注|
|---|---|---|---|
|一级|!important|10000|无条件优先的属性，会覆盖页面内其他任何位置定义的元素样式，慎用|
|二级|行内样式（ style=” ” ）|1000|会造成css难以管理，不推荐使用|
|三级|id选择器|100|#content|
|四级|类选择器、伪类选择器、属性选择器|10|比如： .content、:hover、:first-child|
|五级|标签选择器、伪元素选择器|1|比如：div、p、:before|
|六级|其他选择器|0|* 空格 + > ~|

### 三. 优先规则

有两条或多条样式作用于同一个元素时，权重高的那条样式对元素起作用；权重相同的，则根据就近原则的样式优先，就近原则也相同时，则后定义的样式优先。

就近原则的优先级是：

- 行内式 —— 标签内的`style`属性；
- 内嵌式 —— `<head>`标签内的`<style>`标签；
- 外链式 —— `<link>`标签引入的外部css样式文件；
- 导入式 —— `@import`导入引入的外部css样式文件；

### 四. 实例解析

**CSS样式优先级之间的权重比较采用的是求和比大小的模式。** 所以来看两个典型的实例：

#### 4.1 实例一

```javascript
<style type="text/css">
    div{
        color:red !important;
    }        
</style>
...
<div style="color:blue">我是一行严肃的占位文字</div>
```

内嵌式的权重值为10000+1，下面的行内式的权重值为1000，所以文字的最终颜色为red。

#### 4.2 实例二

```javascript
<style type="text/css">
    #content div.content_left p{
        color:red;    
    }
    #content .content_left p{
        color:blue;
    }
</style>
......
<div id="content">
    <div class="content_left">
        <p>我是一行严肃的占位文字</p>
    </div>
</div>
```

第一条样式的权重计算：100+1+10+1，结果为112；  
第二条样式的权重计算：100+10+1，结果为111。  
所以段落p的最终颜色为red。
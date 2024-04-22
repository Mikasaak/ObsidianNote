---
date_created: 2024-04-7日 星期日 , 02:39:21 下午
date_modified: 2024-04-7日 星期日 , 03:17:33 下午
---
**CSS3的新特性大致分为以下六大类  
  
1.CSS3选择器  
  
2.CSS3边框与圆角  
  
3.CSS3背景与渐变  
  
4.CSS3过渡  
  
5.CSS3变换  
  
6.CSS3动画  
  
  
下面分别说一说以上六类都有哪些内容**

## CSS3选择器



### 1.属性选择器

**1.element[attribute]**

为带有attribute属性的元素设置样式

**2.element[attribute='value']**

为attribute='value'属性的元素设置样式

**3.element[attribute~='value']**

选择attribute属性值包含 单词value的元素 并设置样式

**4.element[attribute*='value']**

选择attribute属性值包含value的元素设置样式

**5.element[attribute^='value']**

选择attribute属性值是以value开头的元素

**6.element[attribute$='value']**

选择attribute属性值是以value结尾的元素

**PS：注意比较3和4的区别**

  

### 2.伪类选择器

#### 动态伪类

定义：这些伪类并不存在于HTML中，只有当用户和网站交互的时候才能体现出来。

1.锚点伪类

```text
:link   
:visited
```

2.用户行为伪类

```text
:hover
:active
:focus
```

3.目标伪类

```text
:target
当我们点击锚点链接时，对应id的元素会显示在视口
```

4.checked状态伪类

这里我们需要知道checkbox只能设置宽高，不能设置背景和边框，如果想要设置那么我们需要用appearance:none;来清除input的默认样式

  

#### CSS3结构类：nth选择器

**：first-child/last-child**

语法 element:first-child

选择属于父元素的首个/最后一个子元素的每个element元素，注意element为子元素。

**：nth-child(n)**

选择某元素下的第n个element元素（n是一个简单的表达式，不能用其他的字母代替），括号里还可以传odd和even两个关键字

**：nth-last-child(n)**

匹配属于某元素下的第n个element子元素，从最后一个子元素开始计数

**：nth-of-type(n)**

语法 element:nth-of-type(n)

匹配属于父元素的特定类型的第n个子元素,element为指定类型的子元素

**:nth-last-of-type**

匹配属于父元素的特定类型的第n个子元素，从最后一个计数

**:first-of-type/:last-of-type**

匹配属于其父元素的特定类型的首个/最后一个子元素的每个元素

**：only-child**

匹配属于父元素的唯一子元素的每个元素

**：only-of-type**

匹配属于其父元素特定类型的唯一子元素的每个元素

**：empty**

匹配没有子元素（包括文本节点）的每个元素

  

#### 复合选择器：
允许选择器根据是否匹配某些条件来选择元素，
**：not**
[:not() - CSS：层叠样式表 | MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:not)
定义：匹配非 元素或者选择器 的每个元素

语法：父元素：not(子元素或者选择器)

例：ul:not(span){}

**：is()**
[:is() - CSS：层叠样式表 | MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:is)
定义：匹配与提供的选择器列表中的任何一个匹配的每个元素。
语法：`:is(selector1, selector2, ...)`
例： 
```css
:is(h1, h2, h3) {
    /* CSS 样式 */
}

```
**：has()**
[:has() - CSS：层叠样式表 | MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:has)

**：where()**
[:where() - CSS：层叠样式表 | MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:where)
定义：类似于 `:is()`，允许将多个选择器组合成一个复合选择器，但在 CSS 中没有被广泛支持。
语法：:where(selector1, selector2, ...)
例：
```css
:where(h1, h2, h3) {
    /* CSS 样式 */
}

```



  

#### 伪元素(也可以使用：)

**element::first-line**

定义：对元素的第一行文本进行设置，只能用于块级元素

**element::first-letter**

定义：用于向文本的首字母设置特殊样式，只能用于块级元素

**element::after**

定义：在元素的内容后面插入新内容，常与content配合使用

**element::selection**

定义：用于设置浏览器中选中文本后的背景色与前景色

  

**伪元素与元素的区别:**

无法通过JS获取其DOM

无法通过浏览器开发者工具直接查看

伪元素默认是 inline

**使用伪元素注意事项：**
> [!attention]
> ::before 不是css3新特性


1.使用伪元素before,after必须设置content

2.使用伪元素before,after显示背景图，一定要使用display设置为块元素

3.使用伪元素before,after设置为display:inline-block,需要再次设置vertical-align:middle

  

## CSS3边框与圆角

### 1.CSS3圆角border-radius

定义：可以为元素添加圆角边框（块元素，行内块元素，行内元素）

属性：

border-top-left-radius 左上角

border-top-right-radius 右上角

border-bottom-right-radius 右下角

border-bottom-left-radius 左下角

复合属性：border-radius：

属性值

四个值：左上角 右上角 右下角 左下角

三个值：左上角 右上角和左下角 右下角

两个值：左上角和右下角 右上角和左下角

一个值：4个角都生效

border-radius中的属性值由两个参数值构成: value1 / value2，值之间用/分隔，value1代表圆角的水平半径，value2代表圆角的垂直半径。

圆形与椭圆：

一旦使用百分比，参照的是元素本身的高度与宽度

当拿50%时，宽等于高为圆形 宽不等于高为椭圆形

### 2.盒阴影box-shadow

定义：可以控制一个或多个下拉阴影的框

语法：box-shadow: 水平方向的偏移量 垂直方向的偏移量 模糊程度 扩展程度 颜色 是否具有内阴影

属性值的介绍：

偏移量：

```text
把元素左上角（0，0）作为基准点，找水

平方向和垂直方向的偏移量

水平： 正值 --- 右 ，负值 --- 左

垂直： 正值 --- 下 ，负值 --- 上
```

  
模糊程度：

```text
边界模糊，但是边界线未动
由边界线向外模糊多少像素
```

  
扩展程度：

```text
盒子阴影，上下左右都向外扩展多少像素
```

是否具有内阴影：

```text
inset(默认没有，也就是默认是外阴影)
加上inset,盒子的阴影为内阴影
扩展程度可为负值，但是模糊程度不可以  
```

## CSS3背景与渐变

### 1.CSS3背景

#### background-image

语法：

```text
backgroundimage:url('1.jpg),url('2.jpg')
```

使用逗号把图片分开

注意：元素引入多个背景图片，前面图片会覆盖后面的图片

#### background-cilp

定义：指定背景的绘制区域（裁剪）

语法：

```text
background-cilp：border-box / padding-box / content-box
```

属性介绍：

```text
border-box：背景被裁剪到边框盒（从边框开始绘制背景图片）---默认
padding-box：背景被裁剪到内边距框（从内边距开始绘制背景图片）
content-box：背景被裁剪到内容框
```

#### background-origin

定义：设置背景图像的原始起始位置

语法：

```text
background-origin：border-box / padding-box / content-box(背景图片坐标原点与这三个有关系)
```

属性的介绍：

```text
border-box：相对于边框来定位
padding-box：相对于内边距来定位
content-box：相对于内容框来定位
```

另外有一个需要了解

```text
background-position:定义背景图片的位置，水平与垂直方向上面的偏移量(参考点)
```

#### background-repeat

定义：设置是否及如何重复背景图像，默认地，背景图像在水平和垂直方向上重复。

属性值：

```text
repeat 默认。背景图像将在垂直方向和水平方向重复。
repeat-x 背景图像将在水平方向重复。
repeat-y 背景图像将在垂直方向重复。
no-repeat 背景图像将仅显示一次。
inherit 规定应该从父元素继承 background-repeat 属性的设置
```

#### background-size

定义：指定背景图像的大小

语法：

```text
background-size：number / % / cover / contain
```

属性介绍：

```text
number: 宽度 高度（如果只写一个数值，第二个数值默认auto）
百分比： 0% - 100% 之间的任何值，此时的百分比参照于元素div的大小
cover：将背景图片等比缩放以填满整个容器（最远边），如果高度达到一定比例100%，宽度多出的会溢出，但是，具体那部分溢出取决于定位
contain：将背景图片等比缩放至某一边紧贴容器边缘为止（最近边），如果图片高度比较小，高度就会有空白区域出现
```

#### 复合属性background

定义：可以在一个声明中设置所有的背景属性

语法：

```text
background：color position size repeat origin clip attachment image; background: #abc center 50% no-repeat content-box content-box fixed url('1.jpg') ,url('2.jpg')...
```
此属性是一个 [简写属性](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Shorthand_properties)，可以在一次声明中定义一个或多个属性：[`background-clip`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-clip)、[`background-color`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-color)、[`background-image`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-image)、[`background-origin`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-origin)、[`background-position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-position)、[`background-repeat`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-repeat)、[`background-size`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-size)，和 [`background-attachment`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-attachment)。

对于所有简写属性，任何没有被指定的值都会被设定为它们的 [初始值](https://developer.mozilla.org/zh-CN/docs/Web/CSS/initial_value)。

> [!tip]
>   `background` 属性被指定多个背景层时，使用逗号分隔每个背景层。


### 2.CSS3渐变

定义：可以在两个或者多个指定颜色之间显示平移的过渡

#### 线性渐变

定义：是沿着一根轴线改变颜色，从起点到终点进行顺序渐变（从一边拉向另一边）

```text
语法：background:linear-gradient(方向，开始颜色，结束颜色)
```

- 方向介绍：

1.方向从上到下（默认）

```css
background: linear-gradient(red,blue);
```

2.方向从左到右

```css
background: linear-gradient(to right,red,blue);
```

3.对角

```css
background: linear-gradient(to right bottom,red,blue);
```

4.角度(单位deg)

```css
background: linear-gradient(角度,red,blue);
```

角度说明：0deg 将创建一个从下到上的渐变，90deg将创建一个从左到右的渐变


- 颜色结点：默认每个颜色均匀分布

```css
background: linear-gradient(red 10%,blue 20%,green 30%,yellow 40%);
```

从0%到10%，为红色，从10%到20%为红色到蓝色的渐变，从20%到30%为蓝色到绿色的渐变，从30%到40%，为绿色到黄色的渐变,从40%到100%为黄色

```text
background: linear-gradient(red 10%,blue);
```

从0%到10%，为红色，从10%到100%为红色到蓝色的渐变

最后如果不写具体数值，默认到100%

```text
background: linear-gradient(red,blue 30%);
```

从0%到30%，为红色到蓝色的渐变

如果第一个不写，默认数值是 0%

```text
background:lineargradient(rgba(255,0,0,0),rgba(255,0,0,1));
```

由透明色变为不透明色

- 重复渐变

示例：background: repeating-linear-gradient(90deg,red 0%,blue 20%);或者 background: repeating-linear-gradient(90deg,red 0%,blue 10%,red 20%);

注意：把元素的整体宽度看成100%

#### 径向渐变

定义：从起点到终点，颜色从内向外进行圆形渐变

语法：background:radial-gradient(形状尺寸，开始颜色，结束颜色)

- 形状分类：

circle --- 圆形

ellipse --- 椭圆形

注意：当元素的高和宽一样时，参数无论设置哪个，都是圆形

- 尺寸大小：

closest-side最近边

```css
background: radial-gradient(closest-side circle,red , blue);
```

farthest-side 最远边

```css
background: radial-gradient(farthest-side circle,red , blue);
```

closest-corner最近角

```css
background: radial-gradient(closest-corner circle,red , blue);
```

farthest-corner最远角

```css
background: radial-gradient(farthest-corner circle,red , blue);
```

- 颜色结点：

例：

```css
background:radial-gradient(circle,red 50% ,blue 70%);
```

注意：此时的百分比,指的是圆心到元素最远端的距离（角度）

- 重复渐变 ：

示例： background: repeating-radial-gradient(red 0%,blue 20%);

background: repeating-radial-gradient(red 0%,blue 10%,red 20%);

  

## CSS3过渡

定义：允许css的属性值在一定时间区间内平滑的过渡，在鼠标点击，鼠标滑过或对元素任何改变中触发，并圆滑地以动画形式改变css的属性值。

属性：

### 1.transition-property属性

定义：设置对象中的参与过渡的属性

语法：transition-property：none | all | property

参数说明：

none： 没有属性改变

all : 默认值，所有属性都改变

property： 元素的属性名 width,color等

### 2.transition-duration属性

定义: 设置对象过渡的持续时间

语法：transition-duration：time

参数说明：

规定完成过渡效果需要花费的时间，以秒或者毫秒计，默认值0

### 3.transition-timing-function属性

定义：设置对象中过渡的动画类型，即规定过渡效果的速度曲线。

该属性允许过渡效果随着时间来改变其速度。

语法：只能使用一个属性值

```text
transition-timing-function: linear|ease|ease-in|ease-out|ease-in-out|cubic-
bezier(n,n,n,n);
```

参数说明：

ease:平滑过渡（0--慢--快--慢），默认值

cubic-bezier(0.25,0.1,0.25,1)

linear:线性过渡（匀速） cubic-bezier(0,0,1,1)

ease-in:慢--快 cubic-bezier(0.42,0,1,1)

ease-out:快--慢 cubic-bezier(0,0,0.58,1)

ease-in-out:慢--快--慢

cubic-bezier(0.42,0,0.58,1)

贝塞尔曲线 :[https://cubic-bezier.com/#.17,.67,.83,.67](https://cubic-bezier.com/#.17,.67,.83,.67)

|值||
|---|---|
|linear|规定以相同速度开始至结束的过渡效果（等于 cubic-bezier(0,0,1,1)）。|
|ease|规定慢速开始，然后变快，然后慢速结束的过渡效果（cubic-bezier(0.25,0.1,0.25,1)）。|
|ease-in|规定以慢速开始的过渡效果（等于 cubic-bezier(0.42,0,1,1)）。|
|ease-out|规定以慢速结束的过渡效果（等于 cubic-bezier(0,0,0.58,1)）。|
|ease-in-out|规定以慢速开始和结束的过渡效果（等于 cubic-bezier(0.42,0,0.58,1)）。|
|cubic-bezier(n,n,n,n)|在 cubic-bezier 函数中定义自己的值。可能的值是 0 至 1 之间的数值。|

#### 亲自试一试 - 实例
  
实例 1**  
  
为了更好地理解不同的函数值，请看下面带有五个不同值的五个不同的 div 元素：

```css
#div1 {transition-timing-function: linear;}
#div2 {transition-timing-function: ease;}
#div3 {transition-timing-function: ease-in;}
#div4 {transition-timing-function: ease-out;}
#div5 {transition-timing-function: ease-in-out;}
/* Firefox 4: */
#div1 {-moz-transition-timing-function: linear;}
#div2 {-moz-transition-timing-function: ease;}
#div3 {-moz-transition-timing-function: ease-in;}
#div4 {-moz-transition-timing-function: ease-out;}
#div5 {-moz-transition-timing-function: ease-in-out;}
/* Safari and Chrome: */
#div1 {-webkit-transition-timing-function: linear;}
#div2 {-webkit-transition-timing-function: ease;}
#div3 {-webkit-transition-timing-function: ease-in;}
#div4 {-webkit-transition-timing-function: ease-out;}
#div5 {-webkit-transition-timing-function: ease-in-out;}
/* Opera: */
#div1 {-o-transition-timing-function: linear;}
#div2 {-o-transition-timing-function: ease;}
#div3 {-o-transition-timing-function: ease-in;}
#div4 {-o-transition-timing-function: ease-out;}
#div5 {-o-transition-timing-function: ease-in-out;}
```

**实例 2  
  
**与上例相同，但通过 cubic-bezier 来规定速度曲线：

```css
#div1 {transition-timing-function: cubic-bezier(0,0,1,1;}
#div2 {transition-timing-function: cubic-bezier(0.25,0.1,0.25,1);}
#div3 {transition-timing-function: cubic-bezier(0.42,0,1,1);}
#div4 {transition-timing-function: cubic-bezier(0,0,0.58,1);}
#div5 {transition-timing-function: cubic-bezier(0.42,0,0.58,1);}
/* Firefox 4: */
#div1 {-moz-transition-timing-function: cubic-bezier(0,0,0.25,1);}
#div2 {-moz-transition-timing-function: cubic-bezier(0.25,0.1,0.25,1);}
#div3 {-moz-transition-timing-function: cubic-bezier(0.42,0,1,1);}
#div4 {-moz-transition-timing-function: cubic-bezier(0,0,0.58,1);}
#div5 {-moz-transition-timing-function: cubic-bezier(0.42,0,0.58,1);}
/* Safari and Chrome: */
#div1 {-webkit-transition-timing-function: cubic-bezier(0,0,1,1;}
#div2 {-webkit-transition-timing-function: cubic-bezier(0.25,0.1,0.25,1);}
#div3 {-webkit-transition-timing-function: cubic-bezier(0.42,0,1,1);}
#div4 {-webkit-transition-timing-function: cubic-bezier(0,0,0.58,1);}
#div5 {-webkit-transition-timing-function: cubic-bezier(0.42,0,0.58,1);}
/* Opera: */
#div1 {-o-transition-timing-function: cubic-bezier(0,0,1,1;}
#div2 {-o-transition-timing-function: cubic-bezier(0.25,0.1,0.25,1);}
#div3 {-o-transition-timing-function: cubic-bezier(0.42,0,1,1);}
#div4 {-o-transition-timing-function: cubic-bezier(0,0,0.58,1);}
#div5 {-o-transition-timing-function: cubic-bezier(0.42,0,0.58,1);}
```

### 4.transition-delay属性

定义：设置对象延迟的过渡时间

语法：transition-delay：time

参数说明：

指定秒或者毫秒数来延迟动画效果的开始，默认是0

### 5.transition复合属性

语法：

transition ： property duration timing-function delay；

参数说明：过渡时间和延迟时间的顺序不能乱

  

## CSS3变换

定义：让一个元素在一个坐标系统中变形，这个属性包含一系列的变形函数，可以移动，旋转，缩放元素。

语法：transform：none | \<transform-function> 默认值是none

### 2d变换

#### 1.rotate()旋转

定义：通过指定一个角度参数，对元素指定一个2D的旋转

语法：transform：rotate(angle) 单位deg

参数说明：angle指旋转角度，正数表示顺时针旋转，负数表示逆时针旋转

#### 2.translate()平移

定义：根据X轴和Y轴的位置给定参数，使当前元素位置移动

分类：

translateX() 仅水平方向移动

语法：transform：translateX() 单位px

translateY() 仅垂直方向移动

语法：transform：translateY() 单位px

translate(x,y) 水平方向和垂直方向同时移动

语法：transform：translate( X, Y) 单位px

注意：如果只写一个参数，第二个默认是0，也就是只设置了水平方向上的位移

#### 3.scale( )缩放

定义：设置元素的缩放程度

分类：

scaleX( ) 仅水平方向缩放

语法：transform：scaleX() 没有单位

scaleY( ) 仅垂直方向缩放

子主题 语法：transform：scaleY() 没有单位

scale(x,y) 使元素水平和垂直方向同时缩放

语法：transform：scale(x,y) 没有单位

#### 4.skew()扭曲/倾斜

定义：设置元素的倾斜状态

分类：

skewX( ) 仅使元素在水平方向上扭曲变形 单位deg 正值 ----逆时针

skewY( ) 仅使元素在垂直方向上扭曲变形 单位deg 正值 ----顺时针

skew( ) 使元素在水平方向和垂直方向上扭曲变形 单位deg

注意：0deg与180deg 效果一样

#### 5.变换基点

定义：元素变换的基准点

语法： transform-origin：水平方向 垂直方向

参数说明：

left top 左上角 ----四个角均可以

25% top

50px 50px

默认值：

rotate 几何中心点

skew 几何中心点

scale 几何中心点

translate 本身位置

  

### 3d变换

#### 1.开启3d空间
```css
transform-style: preserve-3d;
```

一般给父元素开启  
  
### 2.子元素设置3d变换效果

#### rotate

##### rotateX()

定义：指对象在X轴上的旋转角度（变换基点： 50% 50% 0）

##### rotateY()

定义：指对象在Y轴上的旋转角度（变换基点： 50% 50% 0）

##### rotateZ()

定义：指对象在Z轴上的旋转角度（变换基点： 50% 50% 0）

#### translate

##### translateZ()

定义：指对象在Z轴上面的平移（变换基点： 50% 50% 0）
##### translateX()

定义：指对象在X轴上面的平移
##### translateY()

定义：指对象在Y轴上面的平移

#### scale

##### scaleZ()

定义：指定对象的Z轴缩放（变换基点： 50% 50% 0）(无太大意义，开启3d空间)

### 3.设置景深：实现近大远小

父元素子元素都可以设置

父元素：perspective: 300px;

子元素:

transform:perspective(300px) translateZ(-200px);

注意：景深：可选值：大于或等于0,景深值越大，元素看起来越大

默认值: 0 -- 没有景深 （不能为负值）  
  
  
### 4.变换基点

默认值： 50% 50% 0

transform-origin: top; 关键字表示 ( 50% 0 0 )

注意：立体3d盒子 Z：只能使用具体的长度，不能使用百分比和关键字

### 5.景深中心点：改变观察者视角

perspective-origin: top;

perspective-origin: top right;

### 6.元素背面可见还是不可见

backface-visibility:visible ;（默认值：可见）

backface-visibility: hidden; 不可见

  

## CSS3动画
定义：使元素从一种样式逐渐变化到另外一种样式的效果

### @keyframes

定义：keyframes关键帧，用来决定动画变化的关键位置

注意：keyframes 控制关键位置，并不是所有的位置

语法：@keyframes animationname{

keyframes-selector{

cssStyles;

}

}

animationname：必写项，定义动画的名称

keyframes-selector：必写项，动画持续时间的百分比 0% - 100%之间， 或者使用form和to关键字也可以设置，form代表0%，to代表100%

示例：

  

@keyframes abc {

from{transform: rotate(0)}

50%{transform:rotate(90deg)}

to{transform: rotate(360deg)}

}

### animation属性

#### 1.animation-name属性

设置对象所应用的动画名称

语法：

```text
animation-name：keyframename | none
```

参数说明：

keyframename：指定要绑定到选择器的关键帧的动画名称

#### 2.animation-duration属性

定义：设置对象动画的持续时间

语法：

```text
animation-duration：time
```

参数说明：指定对象播放完成需要花费的时间，默认值是0

#### 3.animation-timing-function属性

定义：设置对象动画的过渡类型，即规定动画的速度曲线

速度曲线定义动画从一套 CSS 样式变为另一套所用的时间。  
速度曲线用于使变化更为平滑。

语法：animation-timing-function: value;

参数说明：与transition-timing-function属性的参数一样  
  
animation-timing-function 使用名为三次贝塞尔（Cubic Bezier）函数的数学函数，来生成速度曲线。您能够在该函数中使用自己的值，也可以预定义的值：

|值|描述|
|---|---|
|linear|动画从头到尾的速度是相同的。|
|ease|默认。动画以低速开始，然后加快，在结束前变慢。|
|ease-in|动画以低速开始。|
|ease-out|动画以低速结束。|
|ease-in-out|动画以低速开始和结束。|
|cubic-bezier(n,n,n,n)|在 cubic-bezier 函数中自己的值。可能的值是从 0 到 1 的数值。|

##### 亲自试一试 - 实例
  
  
实例 1  
  
**为了更好地理解不同的定时函数值，这里提供了设置五个不同值的五个不同的 div 元素：

```text
/* W3C 和 Opera: */
#div1 {animation-timing-function: linear;}
#div2 {animation-timing-function: ease;}
#div3 {animation-timing-function: ease-in;}
#div4 {animation-timing-function: ease-out;}
#div5 {animation-timing-function: ease-in-out;}
/* Firefox: */
#div1 {-moz-animation-timing-function: linear;}
#div2 {-moz-animation-timing-function: ease;}
#div3 {-moz-animation-timing-function: ease-in;}
#div4 {-moz-animation-timing-function: ease-out;}
#div5 {-moz-animation-timing-function: ease-in-out;}
/* Safari 和 Chrome: */
#div1 {-webkit-animation-timing-function: linear;}
#div2 {-webkit-animation-timing-function: ease;}
#div3 {-webkit-animation-timing-function: ease-in;}
#div4 {-webkit-animation-timing-function: ease-out;}
#div5 {-webkit-animation-timing-function: ease-in-out;}
```

**实例 2  
  
**与上例相同，但是通过 cubic-bezier 函数来定义速度曲线：

```text
/* W3C 和 Opera: */
#div1 {animation-timing-function: cubic-bezier(0,0,1,1);}
#div2 {animation-timing-function: cubic-bezier(0.25,0.1,0.25,1);}
#div3 {animation-timing-function: cubic-bezier(0.42,0,1,1);}
#div4 {animation-timing-function: cubic-bezier(0,0,0.58,1);}
#div5 {animation-timing-function: cubic-bezier(0.42,0,0.58,1);}
/* Firefox: */
#div1 {-moz-animation-timing-function: cubic-bezier(0,0,1,1);}
#div2 {-moz-animation-timing-function: cubic-bezier(0.25,0.1,0.25,1);}
#div3 {-moz-animation-timing-function: cubic-bezier(0.42,0,1,1);}
#div4 {-moz-animation-timing-function: cubic-bezier(0,0,0.58,1);}
#div5 {-moz-animation-timing-function: cubic-bezier(0.42,0,0.58,1);}
/* Safari 和 Chrome: */
#div1 {-webkit-animation-timing-function: cubic-bezier(0,0,1,1);}
#div2 {-webkit-animation-timing-function: cubic-bezier(0.25,0.1,0.25,1);}
#div3 {-webkit-animation-timing-function: cubic-bezier(0.42,0,1,1);}
#div4 {-webkit-animation-timing-function: cubic-bezier(0,0,0.58,1);}
#div5 {-webkit-animation-timing-function: cubic-bezier(0.42,0,0.58,1);}
```

  
#### 4.animation-delay属性

定义：设置动画的延迟时间

语法：animation-delay：time

参数说明：可选值，定义动画开始前等待的时间，以秒或者毫秒数计数，默认值是0

#### 5.animation-iteration-count属性

定义：设置对象动画的循环次数

语法：

```css
animation-iteration-count ： infinite | number
```

参数说明：

number为数字，其默认值是1

infinite：无限循环次数

#### 6.animation-direction属性

定义：设置对象动画是否反向运动

语法：

```css
animation-direction：normal , reverse , alternate , alternate-reverse
```

参数说明：

normal : 正常方向

reverse :反向运动

alternate ： 先正常运动在反向运动，并持续交替运行， 需要配合循环属性使用

alternate-reverse ： 先反向运动在正常运动，并持续交替运行， 需要配合循环属性使用

#### 7.animation-play-state属性

定义：指定对象是否正在运行或已暂停

语法：

```text
animation-play-state：paused | running
```

参数说明：

paused ： 指定暂停动画

running : 默认值，制定正在运行的动画

**示例：**鼠标移动到box上暂停动画

\#box:hover{

animation-play-state: paused;

}

#### 8.animation-fill-mode

设置动画结束后的状态

none：默认值。不设置对象动画之外的状态，DOM未进行动画前状态

forwards：设置对象状态为动画结束时的状态，100%或to时，当设置animation-direcdtion为reverse时动画结束后显示为keyframes第一帧

backwards：设置对象状态为动画开始时的状态,（测试显示DOM未进行动画前状态）

both：设置对象状态为动画结束或开始的状态，结束时状态优先

#### 9.animation复合属性（不推荐使用 ）

语法：

```text
animation ： name duration timing-function delay interation-count direction play-state
```

  

**注意：在css3里面，给元素设置圆角、阴影、变换等属性时，尽管外形位置发生改变，但是元素本身大小和位置不变**
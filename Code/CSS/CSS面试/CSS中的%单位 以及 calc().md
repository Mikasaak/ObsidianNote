
[图解CSS：CSS 的值和单位 - 知乎](https://zhuanlan.zhihu.com/p/678388670)
## 百分比单位

CSS 中百分比`%`单位也是一个很重要也是很常用的单位，和`px`、`em`类似，在 CSS 中接受`<length>`值的属性都可以使用`%`单位。但在不同的使用场合，其意义将会有很多地不同。正因如此，要理解`%`这个单位，其关键点是：**百分比是一定要有其对应的参照值**，也就是说，**百分比值是一种相对值，任何时候要分析它的计算值，都需要正确的找到它的参照值**。

言外之意，CSS 中的百分比单值最终计算出来的值是可变的。常见的可以分为以下几个大类：
> [!info] 相关文章
> [[CSS 之包含块]]
> 

### **定位中的百分比**

在 CSS 中用来控制`position`位置的`top`、`right`、`bottom`和`left`都可以使用百分比作为单位。如果它们的值为百分比时，其对应的参照物是[[CSS 之包含块 | 包含快]]（但不一定是其父容器）同方向的`width`或`height`计算。

刚才提到过，定位属性中的参照物：**包含块并不一定是其父容器**。为什么这么说呢？因为在 CSS 中`position`对应的属性值不一样，其对应的包含块也将不同：

- 如果元素为静态（`static`）或相对定位（`relative`），包含块一般是其父容器
- 如果元素为绝对定位（`absolute`），包含块应该是离它最近的`position`为`absolute`、`relative`或`fixed`的祖先元素
- 如果元素为固定定位（`fixed`），包含块就是视窗（`viewport`）

### **盒模型中的百分比**

CSS 中的盒模型对应的属性主要有`height`、`min/max-height`、`width`、`min/max-height`、`padding`、`margin`和`border`等属性。不同的属性其对应的参照物也有所不同。

- `height、min/max-height`属性的值为百分比时，其相对于包含块的`height`进行计算
- `width、min/max-width`属性的值为百分比时，其相对于包含块的`width`进行计算
- `padding`和`margin`相对来说更为复杂一些，如果书写模式是水平的，则相对于包含块的`width`进行计算；如果书写模式是垂直的，则相对于包含块的`height`进行计算

### **文本中的百分比**

在 CSS 中控制文本的属性常见的有`font-size`、`line-height`、`text-indent`、`vertical-align`等。不同的属性其参照物也是有所不同：

- `font-size`是基于父元素中`font-size`进行计算
- `text-align`和`padding`有点类似，和书写模式有一定的关系。如果书写模式是水平的，则相对于`width`进行计算，如果是垂直的，则相对于`height`进行计算
- `line-height`则基于`font-size`进行计算
- `vertical-algin`则基于`line-height`计算

### **边框和圆角中的百分比**

在 CSS 中`border-width`属性是不支持%单位的，但在`border-radius`和`border-image-width`两个属性上是可以使用百分比为单位的。如果在`border-radius`中使用百分比单位，也就是说圆角的半径是通过百分比来进行计算的，即：**水平方向的半径是相对于元素`_width_`计算，垂直方向的 半径是相对于元素高度进行计算**。比如：

```css
.circle{
    width: 200px;
    height: 200px;
    border-radius:50%;
}

.ellipse {
    width: 200px;
    height: 100px;
    border-radius: 50%;
}
```

上面的代码对应的结果如下图所示：

  

![](https://pic4.zhimg.com/v2-b8fc3c20fc02ac7bdd8c3ab8bd236f73_r.jpg)

  

从结果是可以看出来，元素`.circle`的`width`和`height`都是`200px`，当`border-radius: 50%`时，计算出来的值都是`100px`；而`.ellipse`元素的`width`和`height`分别是`200px`和`100px`，当`border-radius`为`50%`时，其计算出来的结果相当于`border-radius: 100px / 50px`（水平方向相对于`width`计算，垂直方向相对于`height`计算）。

对于`border-image-width`来说，相对要简单一些，如果该属性的值是百分比，其计算参照于图像边框区域的大小（包含`border`和`padding`）进行计算。

> 有关于圆角 `border-radius` 更详细的介绍，可以移步阅读《[你不知道的 border-radius](https://juejin.cn/book/7199571709102391328/section/7199845563389444099)》!

### **背景属性中的百分比**

在背景属性中，`background-size`、`background-origin`和`background-position`属性都可以使用百分比作为单位。其中`background-size`则是基于`background-origin`区域的大小进行计算。可以对背景图像进行缩放处理。

对于`background-position`中的百分比，相对而言更为复杂一些，需要通过一些数学公式计算：

```css
（容器尺寸 - 背景图像尺寸）* 百分比值
```

当背景图片尺寸（`background-size`）不做任何的重置（也就是`100% 100%`）时，水平百分比的值等于容器宽度百分比值减去背景图片宽度百分比值。垂直百分比的值等于容器高度百分比值减去背景图片高度百分比值。

假设有一个元素，其`width`是`410px`，`height`是`210px`，使用的背景图片的尺寸是`100px * 100px`。如果，`background-position`的值是`75% 50%`，那么百分比最终计算出来的值是：

- 水平位置（`x`轴）：`(410 - 100) * 75% = 232.5px`
- 垂直位置（`y`轴）：`(210 - 100) * 50% = 55px`

  

![](https://pic1.zhimg.com/v2-68f5963c02d1090b6e48a0bef219453c_r.jpg)

  

如果你的背景图片是通过渐变属性来绘制的话，那么在渐变中的每个颜色的位置也可以使用百分比来设置。对于这部分的计算相对而言细节更多，在这里不做过多的阐述，详细的介绍放到渐变那个章节来介绍。这个只提供一个简单的示例：

```css
background-image: linear-gradient(80deg, red, blue, red, blue, red)
```

如果没有显式指定颜色在渐变线上的位置，这将交给浏览器来确定颜色在渐变线上的位置。最简单的情况下只有两个颜色，颜色`1`将被放置在渐变线`0%`位置（渐变线开始位置），颜色`2`将被放置在`100%`位置处（渐变线的结束点）。如果有三个颜色，那么颜色`1`在渐变线的`0%`，颜色`2`在渐变线的`50%`，颜色`3`在渐变线的`100%`。在上面的这个示例中，有五个颜色，那么它们的位置分别在`0%`、`25%`、`50%`、`75%`和`100%`。它们将沿着渐变线平均分布渐变颜色。

  

![](https://pic1.zhimg.com/v2-47079ad6414be068645716e28e81f49c_r.jpg)

  

> **在渐变中的百分比的计算是相对于渐变线计算**。

### **变换中的百分比**

CSS 中的`transform`属性中的`translate`和`transform-origin`值也可以设置百分比。

- `translateX()`的百分比相对于容器的`width`计算
- `translateY()`的百分比相对于容器的`height`计算
- `transform-origin`中横坐标（`x`）相对于容器的`width`计算；纵坐标（`y`）相对于容器的`height`计算

> 注意，在`translate`还有一个`z`轴的函数`translateZ()`。它是不接受百分比为单位的值。

### **百分比值的继承**

请注意，**当百分比值用于可继承属性时，只有结合参照值计算后的绝对值会被继承，而不是百分比值本身**。例如，一个元素的`font-size`是`14px`，并定义了`line-height:150%;`，那么该元素的下一级子元素继承到的`line-height`就是`21px`，而不会再和子元素自己的`font-size`有关。
## 先列一些影响（坑）

#### 1、transform 会提高普通元素的垂直地位

当两个普通元素由于 `margin` 负值重叠时，后面的元素会覆盖前面的元素。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210330114619138.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0Nhcm9sMjQ2,size_16,color_FFFFFF,t_70)

```css
/* css */
.blue, .pink {
	width: 200px;
	height: 200px;
}
.blue {
	border: 10px solid lightblue;
}
.pink {
	border: 10px solid pink;
	margin-top: -50px;
}
```

```html
<!-- html -->
<div class="blue"></div>
<div class="pink"></div>
```

但如果在前面的元素加上 `transform` 属性，前面的元素反而会覆盖后面的元素。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210330115018377.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0Nhcm9sMjQ2,size_16,color_FFFFFF,t_70)

```css
/* css */
.blue, .pink {
	width: 200px;
	height: 200px;
}
.blue {
	border: 10px solid lightblue;
	transform: scale(1);
}
.pink {
	border: 10px solid pink;
	margin-top: -50px;
}
```

#### 2、transform 会让 fixed 子元素变成类似 absolute 的效果

`fixed` 原本可以让元素不随浏览器滚动条进行滚动。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210330143233733.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0Nhcm9sMjQ2,size_16,color_FFFFFF,t_70)

```css
/* css */
.wrap {
	width: 400px;
	height: 2000px;
	border: 10px solid lightblue;
}
.fixed {
	width: 400px;
	height: 200px;
	background-color: pink;
	position: fixed;
}
```

```html
<!-- html -->
<div class="wrap">
	<div class="fixed"></div>
</div>
```

但如果这个 `fixed` 元素的祖先元素中有一个设置了 `transform` 属性，该元素就会“降级”成 `absolute` 的效果，会随着滚动了。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210330143647878.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0Nhcm9sMjQ2,size_16,color_FFFFFF,t_70)

```css
/* css */
.wrap {
	width: 400px;
	height: 2000px;
	border: 10px solid lightblue;
	transform: scale(1);
}
.fixed {
	width: 400px;
	height: 200px;
	background-color: pink;
	position: fixed;
}
```

#### 3、transform 会影响 absolute 子元素100%宽度的计算基准

原本，`absolute` 元素宽度百分比的计算，是基于最近的非 `static` 定位的祖先元素的宽度。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210330144825571.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0Nhcm9sMjQ2,size_16,color_FFFFFF,t_70)

```css
/* css */
.relative {
	width: 200px;
	height: 200px;
	border: 10px solid lightblue;
	position: relative;
}
.absolute {
	width: 100%;
	height: 200px;
	background-color: pink;
	position: absolute;
}
```

```html
<!-- html -->
<div class="relative">
	<div class="absolute"></div>
</div>
```

但如果在这个 `absolute` 元素和它的非 `static` 定位祖先元素之间，增加一个有 `transform` 属性的元素，那么这个 `absolute` 元素的宽度百分比就会基于这个 `transform` 元素来计算。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210330145032347.png)

```css
/* css */
.relative {
	width: 200px;
	height: 200px;
	border: 10px solid lightblue;
	position: relative;
}
.transform {
	width: 100px;
	transform: scale(1);
}
.absolute {
	width: 100%;
	height: 200px;
	background-color: pink;
	position: absolute;
}
```

```html
<!-- html -->
<div class="relative">
	<div class="transform">
		<div class="absolute"></div>
	</div>
</div>
```

#### 4、transform 会影响 absolute 子元素的定位基准

和上一个类似，原本 `absolute` 元素的定位是基于最近的非 `static` 定位的祖先元素。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210330144825571.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0Nhcm9sMjQ2,size_16,color_FFFFFF,t_70)

```css
/* css */
.relative {
	width: 200px;
	height: 200px;
	border: 10px solid lightblue;
	position: relative;
}
.absolute {
	width: 200px;
	height: 200px;
	background-color: pink;
	position: absolute;
	top: 0;
    left: 0;
}
```

```html
<!-- html -->
<div class="relative">
	<div class="absolute"></div>
</div>
```

但如果在中间加一个有 `transform` 属性的元素，那么这个 `absolute` 元素的定位就会基于这个 `transform` 元素。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210330145716745.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0Nhcm9sMjQ2,size_16,color_FFFFFF,t_70)

```css
/* css */
.relative {
	width: 200px;
	height: 200px;
	border: 10px solid lightblue;
	position: relative;
}
.transform {
	transform: translate(50px, 50px);
}
.absolute {
	width: 200px;
	height: 200px;
	background-color: pink;
	position: absolute;
	top: 0;
    left: 0;
}
```

```html
<!-- html -->
<div class="relative">
	<div class="transform">
		<div class="absolute"></div>
	</div>
</div>
```

#### 5、transform 会改变 overflow 对 absolute 元素的限制

原本，一个 `overflow` 不为 `visible` 的元素，如果有一个 `absolute` 子元素，且它们之间（包括 `overflow` 元素自身）没有元素设置了非 `static` 定位属性，那么 `overflow` 对这个 `absolute` 子元素不起作用。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021033015020955.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0Nhcm9sMjQ2,size_16,color_FFFFFF,t_70)

```css
/* css */
.overfolw {
	width: 200px;
	height: 200px;
	border: 10px solid lightblue;
	overflow: hidden;
}
.absolute {
	width: 300px;
	height: 200px;
	background-color: pink;
	position: absolute;
}
```

```html
<!-- html -->
<div class="overfolw">
	<div class="absolute"></div>
</div>
```

但如果它们之间的元素（或 `overflow` 元素自身）设置了 `transform` 属性，那么 `overflow` 就会有效果。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210330144825571.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0Nhcm9sMjQ2,size_16,color_FFFFFF,t_70)

```css
/* css */
.overfolw {
	width: 200px;
	height: 200px;
	border: 10px solid lightblue;
	overflow: hidden;
}
.transform {
	transform: scale(1);
}
.absolute {
	width: 300px;
	height: 200px;
	background-color: pink;
	position: absolute;
}
```

```html
<!-- html -->
<div class="overfolw transform">
	<div class="absolute"></div>
</div>
```

## 涉及到的一些原理

#### 层叠上下文（对应影响1）

**什么是层叠上下文**

层叠上下文是对 HTML 元素的三维构想，形成了层叠上下文的元素，会比普通元素离用户更“近”。

**什么元素会形成层叠上下文**

根元素 html

z-index 不为 auto 的定位元素

CSS3 的部分属性（包括 transform 不为 none 的元素）

**层叠顺序**

层叠上下文元素和普通元素大致是下图的层叠顺序规则：  
![大致的层叠顺序](https://img-blog.csdnimg.cn/2021033003180563.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0Nhcm9sMjQ2,size_16,color_FFFFFF,t_70#pic_center)

如果层叠上下文元素的 z-index 为正值或负值，那么它的层叠顺序由 z-index 决定；

如果层叠上下文元素不依赖 z-index，那么它的层叠顺序和 z-index 为 0 或 auto 的情况一样。

**一句话总结**

==transform 不是 none 会形成层叠上下文，且和 z-index 没有正负值的定位元素是一个层叠顺序，比普通元素要高。==

#### 包含块（对应影响2、3、4、5）

**包含块的影响**

元素的尺寸和位置经常受到包含块的影响，如 width、height、padding、margin 等属性的百分比计算值，定位元素的偏移值，这些值都是基于该元素的包含块计算的。

**定位元素的包含块是如何确定的**

static / relative / sticky 元素的包含块，是其最近的祖先块元素；

absolute 元素的包含块，是其最近的 position 不为 static 的祖先元素；

fixed 元素的包含块，是视口 viewport；

absolute 或 fixed 元素的包含块也可能是最近的 transform 不为 none 的祖先元素。

**一句话总结**

==position 为 absolute 或 fixed 的元素，其包含块也可能是最近的 transform 不为 none 的祖先元素，而其百分比值、定位是根据包含块计算的，所以其尺寸和位置可能受 transform 祖先元素的影响。==

#### overflow（对应影响5）

CSS2.1规范对overflow的描述：

> This property specifies whether content of a block container element is clipped when it overflows the element’s box. It affects the clipping of all of the element’s content except any descendant elements (and their respective content and descendants) whose containing block is the viewport or an ancestor of the element.

大致意思是，overflow 用于指定块元素容器的内容溢出元素是否被剪裁，但如果这个内容溢出元素的包含块是视口 viewport 或是该 overflow 元素的祖先元素，那么这个内容溢出元素就不会被剪裁。

所以 overflow 元素的 absolute 子元素一般情况下不会被剪裁，除非它们之间的元素（或是 overflow 元素自身）为 absolute 子元素的包含块。

而 absolute 元素的包含块可能是 transform 不为 none 的祖先元素，所以如果在 absolute 子元素和 overflow 元素之间的元素（或是 overflow 元素自身）设置 transform 属性，那么这个 absolute 子元素就会被剪裁了。

**一句话总结：**

==overflow 不剪裁这样的子元素——其包含块为视口或 overflow 元素的祖先元素，而 transform 元素可能成为 absolute 元素的包含块，所以当 overflow 元素和 absolute 子元素之间的元素（或 overflow 元素自身）设置了 transform 属性时，absolute 子元素会被剪裁。==

**参考链接：**  
[CSS3 transform对普通元素的N多渲染影响——张鑫旭](https://www.zhangxinxu.com/wordpress/2015/05/css3-transform-affect/)  
[深入理解CSS中的层叠上下文和层叠顺序——张鑫旭](https://www.zhangxinxu.com/wordpress/2016/01/understand-css-stacking-context-order-z-index/)  
[层叠上下文——MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context)  
[布局和包含块——MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Containing_block)
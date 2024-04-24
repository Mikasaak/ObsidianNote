---
description: 
pubDate:
tags: 
title: URI，URL，URN的区别
date_created: 2024-04-22日 星期一 , 03:52:54 下午
date_modified: 2024-04-22日 星期一 , 08:02:19 晚上
---


**URI包括URL和URN两个类别，URL是URI的子集，所以URL一定是URI，而URI不一定是URL**

> **URI =** Universal Resource Identifier 统一资源[标志符](https://so.csdn.net/so/search?q=%E6%A0%87%E5%BF%97%E7%AC%A6&spm=1001.2101.3001.7020)，用来标识抽象或物理资源的一个紧凑字符串。通过使用位置，名称或两者来标识Internet上的资源；它允许统一识别资源。有两种类型的URI，统一资源标识符（URL）和统一资源名称（URN）。**同样定义了资源的标识。但不同点在于URI通常不会包含获取资源的方式。**

> **URL =** Universal Resource Locator 统一资源定位符，一种定位资源的主要访问机制的[字符串](https://so.csdn.net/so/search?q=%E5%AD%97%E7%AC%A6%E4%B8%B2&spm=1001.2101.3001.7020)，用于指示资源的位置以及用于访问它的协议。**通俗来说，就是对于某种web资源的引用，并且包含了如何获取该资源的方式。 最常见到的场景就是指一个网站的地址，也就是你在浏览器地址栏见到的那个东西。** URL，用地址定位

> **URN =** Universal Resource Name 统一资源名称，通过特定命名空间中的唯一名称或ID来标识资源。URN 用名称定位。

**大白话，就是**URI是抽象的定义，不管用什么方法表示，只要能定位一个资源，就叫URI，本来设想的的使用两种方法定位：1，URL，用地址定位；2，URN 用名称定位。

**URI包括URL和URN，后来URN没流行起来，导致几乎目前所有的URL都是URI。**  
![[Pasted image 20240422193649.png|300]]

EX：

> 个人的身份证号就是URN，个人的家庭地址就是URL，URN可以唯一标识一个人，而URL可以告诉邮递员怎么把货送到你手里。

EX：

> https://blog.csdn.net/是个URL，通过这个网址可以找到CSDN，并且还告诉用HTTP协议访问。

### 详细说明URI：

#### 什么是 URI？
什么是 `URI`，与 `URL` 类似，[统一资源标志符](https://xie.infoq.cn/link?target=https%3A%2F%2Fzh.wikipedia.org%2Fwiki%2F%25E7%25BB%259F%25E4%25B8%2580%25E8%25B5%2584%25E6%25BA%2590%25E6%25A0%2587%25E5%25BF%2597%25E7%25AC%25A6)（`Uniform Resource Identifier`，缩写：`URI`），提供了一种识别资源的方法。但与 `URL` 不同的是，`URI` 不提供定位所述资源的方法。

`URI` 的最常见的形式是统一资源定位符（`URL`），经常指定为非正式的网址。由此，可以看出 `URI` 是 `URL` 的超集，并且每个 `URL` 本质上也是一个 `URI`。

**URI，** 指能够唯一的标记一个网络资源的符号。不管用什么方法表示，只要能唯一标记某个资源，它就叫URI。

**URI的组成：**

> URI通常由三部分组成：  
> ①资源的命名机制；  
> ②存放资源的主机名；  
> ③资源自身的名称。

（注意：这只是一般URI资源的命名方式，只要是可以唯一标识资源的都被称为URI，上面三条合在一起是URI的充分不必要条件）

**URI举例：**

> 如：https://blog.csdn.net/qq_32595453/article/details/79516787  
> 我们可以这样解释它：  
> ①这是一个可以通过https协议访问的资源，  
> ②位于主机 blog.csdn.net上，  
> ③通过“/qq_32595453/article/details/79516787”可以对该资源进行唯一标识（注意，这个不一定是完整的路径）

注意：以上三点只不过是对实例的解释，以上三点并不是URI的必要条件，URI只是一种概念，怎样实现无所谓，只要它唯一标识一个资源就可以了。

### 详细说明URL：

#### 什么是 URL？

[统一资源定位符](https://xie.infoq.cn/link?target=https%3A%2F%2Fzh.wikipedia.org%2Fwiki%2F%25E7%25BB%259F%25E4%25B8%2580%25E8%25B5%2584%25E6%25BA%2590%25E5%25AE%259A%25E4%25BD%258D%25E7%25AC%25A6)（`Uniform Resource Locator`，缩写：`URL`），是对资源的引用和访问该资源的方法。俗称网址，就是浏览器地址栏里面的。
![[Pasted image 20240422194517.png]]

一个 `URL` 由以下不同的部分组成：
  
- **协议**：通常是 [https](https://xie.infoq.cn/article/6d47198bee1ad2bc90f6e5151) 或 http，一种告诉浏览器或者设备如何访问资源的方法，当然还有其他的协议，如 `ftp` 、`mailto` 或者 `file`。
    
- 接下来是 `://` 。
    
- **主机名**：表示 IP 地址的注册名称（域名） 或 IP 地址，用于识别连接到网络的设备的数字标识符。
    
- 后面是可选的端口好，前面是冒号 `：` 。
    
- **路径**：可以引用文件系统路径，通常作为一个代码段使用。
    
- **参数**：以问号开头的可选查询参数，其中多个参数用 `&` 连接
    
- **hash**：用于为页面上的标题提供快速链接，如锚点链接。
    

上面是 **URL** 组成部份的简介，为了更加直观，如下图所示：

  ![[Pasted image 20240422194609.png]]

**URL，** 是通过网络路径地址标记资源的符号。可以理解为：URL就是资源的地址。这个资源可以是一个 HTML 页面，一个 CSS 文档，一幅图像等等。  
**URL只是URI的实现方法之一。当然也可以使用其他方法实现URI，只是URL现在比较流行而已。可见，URL是URI的子集。**

**URL的一般格式为(带方括号[]的为可选项)：**

> protocol : // hostname[:port] / path / [;parameters][?query]#fragment

**URL的格式由三部分组成：（ 协议+//+域名+端口+路径+文件+?+参数+#+锚定 ）**

> ①第一部分是协议(或称为服务方式)。  
> ②第二部分是存有该资源的主机IP地址(有时也包括端口号)。  
> ③第三部分是主机资源的具体地址，如目录和文件名等。
> 
> 第一部分和第二部分用“: //”符号隔开，  
> 第二部分和第三部分用“/”符号隔开。  
> 第一部分和第二部分是不可缺少的，第三部分有时可以省略。

**URL举例：**

> http://www.aspxfans.com:8080/news/day01/index.asp?boardID=5&pwd=24618&page=1#name
> 
> 协议部分 http:  
> 域名部分 www.aspxfans.com  
> 端口部分 :8080  
> 目录部分 /news/day01/  
> 文件部分 index.asp  
> 参数部分 boardID=5&pwd=24618&page=1  
> 锚定部分 name

### 什么是 URN？

统一资源名称（`Uniform Resource Name`，缩写：`URN`）是统一资源标识（`URI`）的历史名字，使用 `urn:` 作为 `URI` 方案。

`URN` 也是 `URI` 的子集。`URN` 的一个最好的例子是 `ISBN` 号，它被用来唯一地识别一本书。`URN` 与 `URL` 完全不同，因为它不包含任何协议。

### URI和URL的区别：

URI和URL都定义了资源是什么，但URL还定义了该如何访问资源。URL是一种具体的URI，它是URI的一个子集，它不仅唯一标识资源，而且还提供了定位该资源的信息。URI是一种语义上的抽象概念，可以是绝对的，也可以是相对的，而URL则必须提供足够的信息来定位，是绝对的。

**协议区别：**

> URL指定要使用的协议类型，而URI不涉及协议规范。

**通俗来讲：**

> 拿人做例子：身份证号才是URI，通过身份证号能让我们能且仅能确定一个人。  
> 那统一资源定位符URL是什么呢。也拿人做例子然后跟HTTP的URL做类比，就可以有：动物住址协议://地球/中国/浙江省/杭州市/西湖区/某大学/14号宿舍楼/525号寝/张三.人  
> 可以看到，这个字符串同样标识出了唯一的一个人，起到了URI的作用，所以URL是URI的子集。URL是以描述人的位置来唯一确定一个人的。

在前面《[JavaScript中的Set数据操作](https://xie.infoq.cn/article/67b3576a9148fd6f138dcd3a9)》中介绍过使用 `Set` 求子集，其实`URL`和`URI`的差异就是一个子集的关系，如下图：

  

![](https://static001.geekbang.org/infoq/6e/6e152cbe1bd5ce95ea4966b3c806acf4.png)

  

实际上，`URL`是`URI`的一种类型，它包括关于如何访问资源的信息。在 RFC3986 中的这样一句话：

  

> 术语“统一资源定位器”（URL）指的是 URI 的子集，除了标识资源外，它还通过描述资源的主要访问机制提供了一种定位资源的方法。

### URI、URN、URL

从集合的角度来考虑，`URN` 和 `URL` 都是 `URI` 的子集，如图所示：

  

![|450](https://static001.geekbang.org/infoq/cc/cc612632312e85687222b8cf6591d78e.png)

  

下面以一个网址为例，清晰的展示`URI`、`URN`、`URL` 三者的内容，可以更加直观的反应三者的关系：

  

![](https://static001.geekbang.org/infoq/b7/b71d78edd8bac3b6ec725e67fcff848f.png)

  

从概念上总结三者的关系的话，如图：

  

![](https://static001.geekbang.org/infoq/64/6465697ec3dc9b8b7d6a2cc261a283c1.png)

  

`URL` ：指定位置的 `URI`  

`URN` ：指定名称的 `URI`  

`URI` ：同时指定名称和位置的 `URI`  

### 总结

- URI是一个广义的概念，包含URN和URL。
- URL关注的是资源的位置，怎样获取资源。也就是说，URL包含了获取资源所需的全部信息。
- URN关注的是资源的名称，而无关资源位置。意味着资源在何处移动或者资源是否还存在，这个名称始终不变。
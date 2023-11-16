# <center>HTML学习笔记</center>

# 一、什么是HTML

HTML 是用来描述网页的一种语言

* HTML 指的是超文本标记语言 (**H**yper **T**ext **M**arkup **L**anguage)
* HTML **不是**一种**编程语言**，而是一种**标记语言** (markup language)
* 标记语言是一套**标记标签**(markup tag)
* HTML 使用**标记标签**来描述网页

# 二、HTML的样式

#### 1.模板

```html
<html>

<head>
<title>我的第一个 HTML 页面</title>
</head>

<body>
<p>body 元素的内容会显示在浏览器中。</p>
<p>title 元素的内容会显示在浏览器的标题栏中。</p>
</body>

</html>
```

#### 2.标签是可以嵌套的

##### 层级关系

* 根元素
* 父元素
* 子元素

# 三、标签

#### 1.基础

* HTML 标题

```html
<h1>This is a heading</h1>
<h2>This is a heading</h2>
<h3>This is a heading</h3>
```

* TML 段落(其中为文本内容)

```html
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
```

* HTML 链接

```html
<a href="https://itawenya.cn/">This is a link</a>
```

* HTML 图像

```html
<img src="https://img0.baidu.com/it/u=3520246642,173509775&fm=253&fmt=auto&app=138&f=JPEG?w=666&h=500" width="104" height="142" />
```

#### 2.单双标签

##### 双标签

* 有开始标签(开放标签)和结束标签(闭合标签)如

```html
<htlm></htlm>
<h1></h1>
<p></P>
```

##### 单标签

* 只有开始标签(开放标签)没有结束标签(闭合标签)且反斜杠可不要(最好加上)

```html
<br>换行
<hr>水平线
```

# 四、元素

#### 1.HTML元素语法

* HTML 元素以**开始标签**起始
* HTML 元素以**结束标签**终止
* **元素的内容**是**开始标签**与**结束标签**之间的内容
* 尖括号是标签，标签和内容合到一起为元素
* 某些 HTML 元素具有**空内容**（empty content）
* 空元素**在开始标签中进行关闭**（以开始标签的结束而结束）
* 大多数 HTML **元素**可拥有**属性**

#### 2.HTML元素的嵌套

* 大多数 HTML 元素可以嵌套（可以包含其他 HTML 元素）

#### 3.自己的理解

* 初识标签是定义功能像是标题换行等等以为发挥作用的只是标签
* 看完元素部分才理解标签和内容所成的元素才能发挥功能
* 一直要找的标签种类其实应该也是元素种类

#### 4.参考手册

* [HTML元素（字母排序）](https://www.w3school.com.cn/tags/index.asp)

* [HTML元素（功能排序）](https://www.w3school.com.cn/tags/html_ref_byfunc.asp)

# 五、属性

**属性为HTML提供附加信息**

#### 1.认识

* HTML 标签可以拥有属性。属性提供了有关 HTML 元素的更多的信息。
* 属性总是以名称/值对的形式出现，比如：name="value"。
* **属性总是在 HTML 元素的开始标签中规定。**

#### 2.一些实例

* HTML 链接由 <a> 标签定义。链接的地址在 href 属性中指定：

 ```html
 <a href="https://itawenya.cn/">This is a link</a>
 ```

#### 3.注意事项

* 使用**小写**属性（属性和属性值对大小写不敏感）
* 始终为属性值**加引号**

#### 4.参考手册

* [HTML标准属性参考手册](https://www.w3school.com.cn/tags/html_ref_standardattributes.asp)

# 六、样式

**style 属性用于改变 HTML 元素的样式**

#### 1.HTML 的 style 属性

##### 1. style 属性的作用：

* 提供了一种改变所有 HTML 元素的样式的通用方法。

* 样式是 HTML 4 引入的，它是一种新的首选的改变 HTML 元素样式的方式。通过 HTML 样式，能够通过使用 style 属性直接将样式添加到 HTML 元素，或者间接地在独立的样式表中（CSS 文件）进行定义。

##### 2.不赞成使用的标签和属性

* 标签

```html
<center>	定义居中的内容。
<font> 和 <basefont>	定义 HTML 字体。
<s> 和 <strike>	定义删除线文本
<u>	定义下划线文本
```

* 属性

```html
align	定义文本的对齐方式
bgcolor	定义背景颜色
color	定义文本颜色
```

**注：这些标签和属性应使用样式代替**

#### 2.样式的实例

* 背景颜色

```html
<html>

<body style="background-color:yellow">
<h2 style="background-color:red">This is a heading</h2>
<p style="background-color:green">This is a paragraph.</p>
</body>

</html>
```

#### 3.HTML CSS

* 外部样式表

当样式需要被应用到很多页面的时候，外部样式表将是理想的选择。使用外部样式表，你就可以**通过更改一个文件来改变整个站点的外观。**

```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```

* 内部样式表

当单个文件需要特别样式时，就可以使用内部样式表。你可以**在 head 部分****通过 <style> 标签定义内部样式表**

```html
<head>

<style type="text/css">
body {background-color: red}
p {margin-left: 20px}
</style>
</head>
```

* **内联样式**

当特殊的样式需要应用到个别元素时，就可以使用内联样式。使用内联样式的方法是**在相关的标签中使用样式属性**。**样式属性可以包含任何 CSS 属性**。以下实例显示出如何改变段落的颜色和左外边距。

```html
<p style="color: red; margin-left: 20px">
This is a paragraph
</p>
```

# 七、HTML链接

### 什么是超文本

超文本的基本特征就是可以超链接文档，可以指向其他位置，该位置可以在当前的文档中、局域网中的其他文档，也可以在因特网上的任何位置的文档中。

* 超链接可以用在目录和主题列表中。
* 超链接可以向浏览者指出有关文档中某个主题的更多信息。
* 超链接（hyper text），或者按照标准叫法称为锚（anchor），是使用 <a> 标签标记的分为两种
  * 锚的一种类型是在文档中创建一个热点，当用户激活或选中（通常是使用鼠标）这个热点时，会导致**浏览器进行链接。浏览器会自动加载并显示同一文档或其他文档中的某个部分，或触发某些与因特网服务相关的操作**，例如发送电子邮件或下载特殊文件等。
  * 锚的另一种类型会**在文档中创建一个标记，该标记可以被超链接引用。**

#### 1.HTML超链接（链接）

超链接可以是一个字，一个词，或者一组词，也可以是一幅图像，您可以点击这些内容来跳转到新的文档或者当前文档中的某个部分。

* 使用 <a> 标签在 HTML 中创建链接，有两种使用 <a> 标签的方式：
  1. 通过使用 href 属性 - 创建指向另一个文档的链接
  2. 通过使用 name 属性 - 创建文档内的书签

* HTML 链接语法

```html
<a href="url">Link text</a>
```

href 属性规定链接的目标。

开始标签和结束标签之间的文字被作为超级链接来显示。

* **target属性**（分情况使用，在w3school的网站上就是本窗口和新窗口打开相结合，GitHub则全为在本窗口打开）

使用 Target 属性，你可以定义被链接的文档在何处显示。

例如：把链接的 target 属性设置为 "_blank"，该链接会在新窗口中打开。

下面的这行会在新窗口打开文档：

```html
<a href="https://itawenya.cn/" target="_blank">Visit W3School!</a>
```

* **name属性**（在目录索引方面应该很有用，希望学习后能优化自己的GitHub索引）

首先，我们在 HTML 文档中**对锚进行命名**（创建一个书签）：

```html
<a name="tips">基本的注意事项 - 有用的提示</a>
```

然后，我们在同一个文档中创建**指向该锚**的链接：

```html
<a href="#tips">有用的提示</a>
```

您也可以在其他页面中创建指向该锚的链接：

```html
<a href="http://www.w3school.com.cn/html/html_links.asp#tips">有用的提示</a>
```

在上面的代码中，我们将 **# 符号和锚名称(用来指向锚)**添加到 URL 的末端，就可以直接链接到 tips 这个命名锚了。

# 八、HTML图像

通过使用 HTML，可以在文档中显示图像。

#### 1.图像标签（<img>）和源属性（Src）

* 在 HTML 中，图像由 <img> 标签定义。
* <img> 是**空标签**，意思是说，它**只包含属性**，并且**没有闭合标签**。
* 要在页面上显示图像，源属性（src）。src 指 "source"。**源属性**的值是**图像的** **URL 地址**。
  * URL 指存储图像的位置
  * 浏览器将**图像显示****在文档中**图像标签出现**的地方**。

* 定义图像的语法

```html
<img src="url" />
```

#### 2.替换文本属性（Alt）

alt 属性用来为图像定义一串**预备的可替换的文本**。替换文本**属性的值**是**用户定义**的。

* Alt的语法

```html
<img src="boat.gif" alt="Big Boat">
```

* Alt的作用

当**浏览器无法载入图像**时，**替换文本属性**可告诉读者他们**失去的信息**。此时，浏览器将**显示**这个**替代性的文本而不是图像。**

#### 3.一些其他例子

##### 1.背景图片

```html
<body background="/i/eg_background.jpg">
```

* **gif** 和 **jpg** 文件均可用作 HTML **背景**。
* 如果**图像小于页面**，**图像会进行重复**。

##### 2.排列图像

```html
<img src="/i/eg_cute.gif" align="bottom">
```

* align="bottom"默认对齐。
* align="middle"中间对齐。
* align="top"靠上对齐。

* align="left"图像将浮动到文本的左侧。
* align="right"图像将浮动到文本的右侧。

##### 3.调整图像尺寸

```html
<img src="/i/eg_mouse.jpg" width="50" height="50">
```

* width="px"
* height=" px"

单位默认为px

##### 4.制作图像链接

```html
<a href="/example/html/lastpage.html">
<img border="0" src="/i/eg_buttonnext.gif" />
</a>
```

把图片元素嵌入链接元素

##### 5.创建图像映射

创建带有可供点击区域的图像地图。其中的每个区域都是一个超级链接

* img 元素中的 "usemap" 属性引用 map 元素中的 "id" 或 "name" 属性（根据浏览器），所以我们同时向 map 元素添加了 "id" 和 "name" 属性。

* 还在学习没有理解坐标的定位
* map标签和其中area的简单理解
  * 在 area 标签上支持的属性有 shape、coords、href、alt、target、type、download、hreflang、media、rel`；
  * coords 值如何精确定位（通过圆心（x，y）和半径r来确定位置和大小
  * 左上角坐标为（0，0）

##### 6.把图像转换为图像映射

​	还没理解

# 九、HTML表格和列表

标签本身较简单，语法理解也较容易可以随时查阅使用方法

* 表格
  * 每个表格由 table 标签开始
  * 每个表格行由 tr 标签开始
  * 每个表格数据由 td 标签开始

```html
<table border="1">
<tr>(行)
<td>列</td>
<td></td>
</tr>
</table>
```

* 列表

1. 无序列表

无序列表始于 <ul> 标签。每个列表项始于 <li>。

```html
<ul>
<li>Coffee</li>
<li>Milk</li>
</ul>
```

2. 有序列表

有序列表始于 <ol> 标签。每个列表项始于 <li> 标签。

```html
<ol>
<li>Coffee</li>
<li>Milk</li>
</ol>
```

3. 定义列表

自定义列表以 <dl> 标签开始。每个自定义列表项以 <dt> 开始。每个自定义列表项的定义以 <dd> 开始。

```html
<dl>
<dt>Coffee</dt>
<dd>Black hot drink</dd>
<dt>Milk</dt>
<dd>White cold drink</dd>
</dl>
```


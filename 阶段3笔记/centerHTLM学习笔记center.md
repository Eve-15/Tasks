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

* 用户代理样式表

用户代理样式表是浏览器（例如，Chrome，Firefox，Edge 等）提供的“默认样式表”，用于以满足**“一般显示期望”**的方式显示页面

<img src="https://img-blog.csdnimg.cn/878abf9b5b074357acfa710b17f9e3b8.png" alt="在这里插入图片描述">

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

# 十、块

**可以通过 <div> 和 <span> 将 HTML 元素组合起来**，大多数HTML元素被定义为**块级元素**或**内联元素**。

#### 1.HTML 块元素(block level element)

* 块级元素在浏览器显示时，通常会以新行来开始（和结束）例如：

  ```html
  <b>, <td>, <a>, <img>
  ```

####     div元素

* HTML <div> 元素是**块级元素**，它是可**用于组合其他 HTML 元素的容器。**
* div元素没有特定的含义。除此之外，由于它属于块级元素，**浏览器会在其前后显示折行**。
* 如果与 CSS 一同使用，<div> 元素可用于**对大的内容块设置样式属性。**
* div 元素的另一个常见的用途是**文档布局**。它取代了使用表格定义布局的老式方法。使用 <table> 元素进行文档布局不是表格的正确用法。<table> 元素的作用是显示表格化的数据。
* 块级元素（block）**只能出现在<body>元素内**，**块级的元素里面不能放块级**，**div除外**。

```html
<div style="color:#00FF00">
  <h3>This is a header</h3>
  <p>This is a paragraph.</p>
</div>
```



#### 2.HTML 内联元素(inline element)

* 内联元素在显示时通常不会以新行开始。(与块级元素有所区别)例如：

```html
<b>, <td>, <a>, <img>
```

* 内联元素分为两种：替换元素和非替换元素。

1. 替换元素

浏览器根据**元素的标签和属性**，来决定其的具体显示内容的元素，常见的有：<img>、<input>、<select><textarea>、<object>。比如浏览器根据<img >标签的**src属性**显示那一张图片，根据<input>的**type属性**决定显示输入框还是按钮，它们的宽度和高度是可以设置的。

2. 非替换元素

内容**直接表现**给用户端的元素称为成为非替换元素，常见的有：<span>、<label>等。例如<span>，它会将**开始和结束标签**中的内容**直接在浏览器上展示**出来。

#### span元素

* HTML <span> 元素是内联元素，可用作文本的容器。
* <span> 元素也没有特定的含义。
* 当与 CSS 一同使用时，<span> 元素可用于为部分文本设置样式属性。
* <span> 标签被用来组合**文档**中的行内元素
* 当对单个元素进行特殊修改时用内联元素

```html
<p class="tip"><span>提示：</span>... ... ...</p>
```

#### 3.块级元素和内联元素的区别

<div class="table-box"><table><thead><tr><th>比对项</th><th>块级元素</th><th>内联元素</th></tr></thead><tbody><tr><td>占位</td><td>独占一行,默认情况下，其宽度自动填满其父元素宽度</td><td>相邻的内联元素会排列在同一行里，直到一行排不下，才会换行，其宽度随元素的内容而变化</td></tr><tr><td>设置width / height是否生效</td><td>生效</td><td>内联元素分为替换元素和非替换元素，替换元素生效，非替换元素无效</td></tr><tr><td>设置padding / margin 是否生效</td><td>生效</td><td>部分生效 只有水平方向上的边距和填充生效：margin-left、margin-right、padding-left、padding-right，其它属性不会起边距效果。</td></tr><tr><td>display</td><td>block(还有table，list-item)</td><td>inline（还有inline-block，inline-table，table-cell）</td></tr></tbody></table></div>

#### 4.块级元素和内联元素的相互转换

```html
display:inline; //转换为内联元素
display:block; //转换为块级元素
display:inline-block; //转换为内联块级元素
```

#### 5.拓展

* 所有的html元素初始值都是内联的，div也不一例外

``` html
<div>hello</div>
<span>world</span>
```

* 内联块

**内联块**元素（inline-block）**同时**具备**内联元素**、**块状元素**的特点，代码**display：inline-block可以将元素设置为内联块元素。**

* 特点

1. **不会独占一行**，相邻的内联元素会排在同一行。
2. **元素的高度，宽度，内外边距都可以设置。**如果**没有设置**宽高，宽高**由内容决定**
3. 代码**换行**，**内联元素之间**会**产生差距**。

#### 6.更多的元素归属

* 主要块级元素

```html
主要块级元素
<address>        定义地址
<caption>        定义表格标题
<dd>        定义列表中定义条目
<div>        定义文档中的分区或节
<dl>        定义列表
<dt>        定义列表中的项目
<fieldset>        定义一个框架集
<form>        创建表单元素
<h1><h2><h3><h4><h5><h6>        标题元素
<hr>        水平线
<legend>        给fieldset元素定义标题
<li>        定义列表项目
<noframes>        为那些不支持框架的浏览器显示文本，放置于frameset标签内
<noscript>        为那些不支持脚本的浏览器显示文本
<ol>        有序列表
<ul>        无序列表
<p>        定义段落
<pre>        定义预格式化文本
<table>        定义表格
<tbody>        定义表格主体
<td>        表格中的标准单元格
<tr>        表格中的行
<tfoot>        表格中的页脚
<th>        定义表头单元格
<thead>        定义表格的表头
```

* 主要内联元素

```html
主要内联元素

<a>        可定义锚以及超链接
<abbr>        表示一个缩写形式
<acronym>        表示只取title中首字母的缩写形式
<b>        字体加粗
<bdo>        可覆盖默认的文本方向
<big>        大号字体加粗
<br>        换行
<cite>        引用进行定义
<code>        定义计算机代码文本
<dfn>        定义一个定义项目
<em>        定义为强调的内容
<i>        斜体文本效果
<img>        向网页中嵌入一张图像
<input>        输入框
<kbd>        定义键盘文本
<label>        为input进行标记/标注
<q>        定义短的引用
<s>    表示不准确不相关，却不应当给予删除的内容
<samp>        定义样本文本
<select>        定义单选或者多选菜单
<small>        呈现小号字体效果
<span>        组合文档中的行内元素
<strong>        语气更强的强调内容
<sub>        定义下标文本
<sup>        定义上标文本
<textarea>        多行文本输入控件
<tt>        打字机或者等宽的文本效果
<var>        定义变量
```

# 十一、类

对 HTML 进行分类（设置类），使我们能够**为元素的类定义 CSS 样式。**

为相同的类设置相同的样式，或者为不同的类设置不同的样式。

* 实例

```html
<style>
.cities {
    background-color:black;
    color:white;
    margin:20px;
    padding:20px;
} 
</style>

<div class="cities">
    ...
</div>
```

```html
<style>
  span.red {color:red;}
</style>

<h1>My <span class="red">Important</span> Heading</h1>
```

注意观察两者**区别**在**头部**时**不同**

# 十二、id

id 属性指定 HTML 元素的唯一 ID。 **id 属性的值**在 HTML 文档中**必须是唯一的**（id 属性的值**区分大小写**）

**id 属性用于指向样式表中的特定样式声明**。JavaScript 也可使用它来访问和操作拥有特定 ID 的元素。

#### 1.id属性的语法

* 写一个**井号 (#)**，**后跟一个 id 名称**。然后，在**花括号 {} 中定义 CSS 属性。**

#### 2.实例（注意理解和感受）

```html
<!DOCTYPE html>
<html>
<head>
<style>
#myHeader {
  background-color: lightblue;
  color: black;
  padding: 40px;
  text-align: center;
}
</style>
</head>
<body>

<h1 id="myHeader">My Header</h1>

</body>
</html>
```

**重点关注#和id同时注意和元素的类，类比理解，注意两者区别**

#### 3.Class与ID的差异

**一个类名**可以由**多个 HTML 元素使用**，而**一个 id 名称**只能**由页面中的**一个 HTML 元素使用

#### 4.通过 ID 和链接实现 HTML 书签

* **HTML 书签**用于让读者**跳转至网页的特定部分。**

* 如果页面很长，那么书签可能很有用。

* 要使用书签，您必须**首先创建它**，然后**为它添加链接。**

* 然后，当**单击链接**时，**页面将滚动到带有书签的位置。**

* 实例

```html
<h2 id="C4">第四章</h2>//首先在想跳转的位置创建书签
<a href="#C4">跳转到第四章</a>//在同一界面向这个书签添加一个链接
```

#### 5.在JavaScript 中使用 id 属性

JavaScript 也可以**使用 id 属性为特定元素执行某些任务。**

JavaScript 可以**使用 getElementById() 方法访问拥有特定 id 的元素**(个人理解为与函数类似事先定义一个内容，在文本中调用)

可以处理文本

* 实例

```html
<script>
function displayResult() {
  document.getElementById("myHeader").innerHTML = "Have a nice day!";
}
</script>


<h1 id="myheader"></h1>
```

# 十三、HTML JavaScript

#### HTML script 标签

* HTML ```<script>``` 标签用于定义客户端脚本（JavaScript）
* ```<script> ```元素即可包含脚本语句，也可通过 src 属性指向外部脚本文件。
* JavaScript 的常见用途是图像处理、表单验证和内容的动态更改

#### JavaScript的一些实例

* **选取 HTML 元素**，JavaScript 最**常用 document.getElementById() . innerHTML =** 的方法

  document.getElementById()表示获取id

  innerHTML =用于获取/设置元素的完整HTML内容

  其作用是将 id 为 "。。。" 的 HTML 元素的内容更改为 "。。。"。

* 这个 JavaScript 示例向 id="demo" 的 HTML 元素内写入 "Hello JavaScript!"：

```html
<script>
document.getElementById("demo").innerHTML = "Hello JavaScript!";
</script>
<p id="demo"></P>
```

* JavaScript 能够更改内容：

```html
<p>JavaScript 可以更改 HTML 元素的内容：</p>

<button type="button" onclick="myFunction()">点击我！</button>

<p id="demo">这是一个演示。</p>

<script>
function myFunction() { 
  document.getElementById("demo").innerHTML = "Hello JavaScript!";
}
</script>
```

onclick:当被点击时会被调用并执行相应的javascript代码

推测当id和内容同时存在应该优先显示id定义的内容

* JavaScript 能够更改属性，下面的例子展示更改了图像的src属性

```html
<script>
function light(sw) {
  var pic;
  if (sw == 0) {
    pic = "/i/eg_bulboff.gif"
  } else {
    pic = "/i/eg_bulbon.gif"
  }
  document.getElementById('myImage').src = pic;
}
</script>

<img id="myImage" src="/i/eg_bulboff.gif" width="109" height="180">

<p>
<button type="button" onclick="light(1)">开灯</button>
<button type="button" onclick="light(0)">关灯</button>
</p>
```

从此处初步接触Java script语法需进一步学习理解含义

* HTML ```<noscript> ```标签

HTML``` <noscript>``` 标签定义了替代内容，这些内容将显示给在浏览器中禁用了脚本或浏览器不支持脚本的用户：

```html
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = "Hello JavaScript!";
</script>

<noscript>抱歉，您的浏览器不支持 JavaScript！</noscript>//为不支持客户端脚本的用户定义替代内容。

<p>不支持 JavaScript 的浏览器将显示 noscript 元素内的文本。</p>
```

注意理解用法及作用即可

# 十四、路径

* < img src="picture.jpg">	picture.jpg (位于与当前网页相同的文件夹)
* < img src="images/picture.jpg">	picture.jpg (位于当前文件夹的 images 文件夹中)

* < img src="/images/picture.jpg">	picture.jpg(当前站点根目录的 images 文件夹中)
* < img src="../picture.jpg">	picture.jpg (位于当前文件夹的上一级文件夹中)


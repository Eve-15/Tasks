# <center>CSS学习笔记</center>

# 一、什么是CSS

* CSS 指**层叠样式表** (Cascading Style Sheets)
* 样式定义**如何显示 HTML 元素**
* 样式通常**存储在样式表**中
* 把样式添加到 HTML 4.0 中，是为了**解决内容与表现分离**的问题
* **外部样式表**可以极大**提高工作效率**
* **外部样式表**通常**存储在 CSS 文件**中
  **多个样式定义可层叠为一个**

**样式表定义如何显示 HTML 元素**，就**像 HTML 中的字体标签和颜色属性所起的作用那样**。样式通常保存在外部的 .css 文件中。我们只需要**编辑一个**简单的 **CSS 文档**就可以**改变所有页面的布局和外观。**

# 二、CSS规则

CSS 规则由**两个主要的部分构成**：**选择器**，以及**一条或多条声明**，如下图：

![img](https://www.runoob.com/wp-content/uploads/2013/07/632877C9-2462-41D6-BD0E-F7317E4C42AC.jpg)

* **选择器通常是**您需要改变样式的 **HTML 元素。**
* **每条声明**由**一个属性**和**一个值**组成。
  * **CSS声明**总是**以分号 ; 结束**，声明总**以大括号 {} 括起来**
  * 为了让CSS**可读性更强**，可以**每行只描述一个属性**
* 属性是希望设置的样式属性。**每个属性有一个值**。**属性和值被冒号分开**。
* CSS**注释以 /* 开始**, **以 */ 结束**

# 三、CSS选择器(结合例子理解并注意规则)

CSS 选择器用于“查找”（或选取）要设置样式的 HTML 元素。

### 1.分类：

我们可以将 CSS 选择器分为五类：

* 简单选择器（根据名称、id、类来选取元素）
* 组合器选择器（根据它们之间的特定关系来选取元素）
* 伪类选择器（根据特定状态选取元素）
* 伪元素选择器（选取元素的一部分并设置其样式）
* 属性选择器（根据属性或属性值来选取元素）

这次主要学习简单的选择器

### 2.简单的选择器：

#### CSS 元素选择器(element)

元素选择器**根据元素名称**来**选择** HTML 元素。

* 实例：页面上的所有 <p> 元素都将居中对齐，并带有红色文本颜色

```css
p {
  text-align: center;
  color: red;
}
```

#### CSS id 选择器(#id)

id 选择器**使用 HTML 元素的 id 属性**来**选择特定元素**

* **元素的 id** 在**页面中是唯一的**，因此 **id 选择器用于选择一个唯一的元素**
* 要**选择**具**有特定 id 的元素**，**写一个井号（＃）**，**后跟该元素的 id**

* 实例：这条 CSS 规则将应用于 id="para1" 的 HTML 元素

```css
<head>
<style>
#para1 {
  text-align: center;
  color: red;
}
</style>
</head>
<body>

<p id="para1">Hello World!</p>
<p>本段不受样式的影响。</p>

</body>
```

**注：id 名称不能以数字开头**

#### CSS 类选择器(.class)

类选择器**选择有特定 class 属性**的 **HTML 元素**

* 如需**选择拥有特定 class 的元素**，请**写一个句点（.）字符，后面跟类名**

* 实例：在此例中，所有带有 class="center" 的 HTML 元素将为红色且居中对齐

```css
<style>
.center {
  text-align: center;
  color: red;
}
</style>
</head>
<body>

<h1 class="center">居中的红色标题</h1>
<p class="center">居中的红色段落。</p> 

</body>
```

* 还可以**指定**只有特定的 HTML 元素会受类的影响，**在类名前的.前加特定的元素名称**如下例子

```css
<head>
<style>
p.center {
  text-align: center;
  color: red;
}
</style>
</head>
<body>

<h1 class="center">这个标题不受影响</h1>
<p class="center">这个段落将是红色并居中对齐的。</p> 

</body>
```

* HTML 元素也可以**引用多个类**

```css
<head>
<style>
p.center {
  text-align: center;
  color: red;
}

p.large {
  font-size: 300%;
}
</style>
</head>
<body>

<h1 class="center">这个标题不受影响</h1>
<p class="center">本段将是红色并居中对齐。</p>//此处为引用一个类
<p class="center large">本段将是红色、居中对齐，并使用大字体。</p>//此处为引用两个类 

</body>
```

在引用多个类时，**类名之间**要用**空格隔开**

经尝试得当**同一属性在不同类名中同时出现**，属性的值**取决于style元素中属性值定义的先后顺序**

#### CSS 通用选择器(*)

**通用选择器（*）**选择**页面上**的**所有**的 **HTML 元素**（会不会略有局限性？）

* 实例下面的 CSS 规则会影响页面上的**每个 HTML 元素**：

```css
<head>
<style>
* {//注意规则和用法
  text-align: center;
  color: blue;
}
</style>
</head>
<body>

<h1>Hello world!</h1>

<p>页面上的每个元素都会受到样式的影响。</p>
<p id="para1">我也是！</p>
<p>还有我！</p>

</body>
```

通过尝试得：当**使用通用选择器时**如果**使用其他选择器**则**优先显示其他选择器**

#### CSS 分组选择器

分组选择器**选取所有具有相同样式定义**的 **HTML 元素**

* 例如：下面的 CSS 代码（h1、h2 和 p 元素具有相同的样式定义）：

```css
h1 {
  text-align: center;
  color: red;
}

h2 {
  text-align: center;
  color: red;
}

p {
  text-align: center;
  color: red;
}
//h1、h2 和 p 元素具有相同的样式定义
```

* 分组实例：对上述代码中的选择器进行分组：

```css
<head>
<style>
h1, h2, p {
  text-align: center;
  color: red;
}
</style>
</head>
<body>

<h1>Hello World!</h1>
<h2>更小的标题</h2>
<p>这是一个段落。</p>

</body>
```

对选择器进行**分组**，**用逗号**来**分隔每个选择器**

对选择器进行**分组**，以最大程度地**缩减代码**。

# 四、CSS 使用

### 1.三种使用 CSS 的方法：

- 外部 CSS
- 内部 CSS
- 行内 CSS

#### 外部 CSS

通过**使用外部样式表**，您只需**修改一个文件**即可**改变整个网站的外观**

**注：**每张 HTML 页面**必须在 head 部分的 <link> 元素内包含对外部样式表文件的引用**

* 实例：外部样式在 HTML 页面 <head> 部分内的 <link> 元素中进行定义：

```css
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```

**外部样式表**可以在**任何文本编辑器中编写**，并且**必须以 .css 扩展名保存**。

**外部 .css 文件不应包含任何 HTML 标签。**

* "mystyle.css" 是这样的：

```css
body {
  background-color: lightblue;
}

h1 {
  color: navy;
  margin-left: 20px;
}
```

**注：请勿在属性值和单位之间添加空格**

#### 内部 CSS

如果**一张 HTML 页面**拥有**唯一的样式**，那么可以使用**内部样式表**

内部样式是**在 head 部分的 <style> 元素中进行定义**

* 实例：内部样式在 HTML 页面的 <head> 部分内的 <style> 元素中进行定义：

```css
<head>
<style>
body {
  background-color: linen;
}

h1 {
  color: maroon;
  margin-left: 40px;
} 
</style>
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
```

#### 行内 CSS

行**内样式（也称内联样式）**可用于**为单个元素应用唯一的样式**

注：使用行内样式，**需将 style 属性添加到相关元素**，**style 属性可包含任何 CSS 属性**。

* 实例：行内样式在相关元素的 "style" 属性中定义：

```css
<body>

<h1 style="color:blue;text-align:center;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>

</body>
```

### 2.多个样式表

**如果在不同样式表中为同一选择器（元素）定义了一些属性，则将使用最后读取的样式表中的值**

* 假设某个***外部样式表***为 <h1> 元素设定的如下样式：

```css
h1 {
  color: navy;
}
```

* 然后，假设某个***内部样式表***也为 <h1> 元素设置了如下样式：

```css
h1 {
  color: orange;    
}
```

* 实例：如果**内部样式**是**在链接到外部样式表之后定义**的，则 <h1> 元素将是内部样式表定义的值：

```css
<head>
<link rel="stylesheet" type="text/css" href="/demo/css/mystyle.css">//先连接外部样式表
<style>
h1 {
  color: orange;//后定义内部样式
}
</style>
</head>
<body>

<h1>这是一个标题</h1>
<p>本文档的样式是外部样式表和内部样式的组合。</p>

</body>
```

* 实例：如果在链接到外部样式表*之前*定义了内部样式，则 <h1> 元素将是外部样式表定义的：

```css
<head>
<style>
h1 {
  color: orange;//先定义内部样式
}
</style>
<link rel="stylesheet" type="text/css" href="/demo/css/mystyle.css">//后连接到外部样式表
</head>
<body>

<h1>这是一个标题</h1>
<p>本文档的样式是外部样式表和内部样式的组合。</p>

</body>
```

### 3.层叠顺序
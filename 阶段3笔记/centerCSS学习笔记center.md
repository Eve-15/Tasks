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

当为某个 HTML 元素指定了多个样式时，会使用何种样式

* 页面中的所有样式将按照以下规则**“层叠”为新的“虚拟”样式表**，其中**第一优先级最高：**

1. 行内样式（在 HTML 元素中）
2. 外部和内部样式表（在 head 部分）
3. 浏览器默认样式

因此，**行内样式（内联样式）具有最高优先级**，并且将覆盖外部和内部样式以及浏览器默认样式。

* 选择器优先级列表（优先级从上至下递增）

1. 通用选择器（*）
2. 元素(类型)选择器
3. 类选择器
4. 属性选择器
5. 伪类
6. ID 选择器
7. 内联样式

# 五、CSS基础样式

### 1.CSS 颜色：

颜色是通过使用预定义的**颜色名称**，或 **RGB、HEX、HSL、RGBA、HSLA 值**

#### CSS 颜色名

* 在 CSS 中，可以使用**颜色名称**来**指定颜色**

#### CSS 背景色

* 实例：可以为 HTML 元素设置背景色：

```css
<h1 style="background-color:DodgerBlue;">China</h1>
<p style="background-color:Tomato;">China is a great country!</p>
```

#### CSS 文本颜色

可以设置**文本**的颜色

* 实例：

```css
<h1 style="color:Tomato;">China</h1>
<p style="color:DodgerBlue;">China is a great country!</p>
<p style="color:MediumSeaGreen;">China, officially the People's Republic of China...</p>
```

#### CSS 边框颜色

可以设置**边框**的颜色

* 实例

```css
<h1 style="border:2px solid Tomato;">Hello World</h1>
<h1 style="border:2px solid DodgerBlue;">Hello World</h1>
<h1 style="border:2px solid Violet;">Hello World</h1>
```

#### CSS 颜色值:

##### 1.CSS RGB 颜色

* rgb(*red*, *green*, *blue*)

每个参数 (*red*、*green* 以及 *blue*) 定义了 0 到 255 之间的颜色强度。

* RGBA 值

RGBA 颜色值是具有 **alpha** 通道的 RGB 颜色值的**扩展** - 它指定了颜色的**不透明度**

* rgba(*red*, *green*, *blue*, *alpha*)

##### 2.CSS HEX 颜色

在 CSS 中，可以使用以下格式的十六进制值指定颜色：

* 其中 rr（红色）、gg（绿色）和 bb（蓝色）是介于 00 和 ff 之间的十六进制值（与十进制 0-255 相同）。

##### 3.CSS HSL 颜色

在 CSS 中，可以使用色相、饱和度和明度（HSL）来指定颜色，格式如下：

* **色相**（hue）是**色轮上从 0 到 360 的度数。0 是红色，120 是绿色，240 是蓝色。**
* **饱和度（**saturation）是**一个百分比值**，**0％ 表示灰色阴影**，而 **100％ 是全色**。
* **亮度（**lightness）也是**百分比**，**0％ 是黑色，50％ 是既不明也不暗，100％是白色。**

HSLA 值

HSLA 颜色值是**带有 Alpha 通道**的 **HSL 颜色值的扩展** - 它**指定了颜色的不透明度**。

* hsla(*hue*, *saturation*, *lightness*, *alpha*)

### 2.CSS 背景:

* background-color
* background-image
* background-repeat
* background-attachment
* background-position

#### CSS background-color(背景颜色)

* `background-color` 属性指定元素的背景色。

* ```opacity ```属性指定元素的**不透明度/透明度**。取值范围为 0.0 - 1.0。值越低，越透明(文字和背景都会应用透明度)

* 使用 RGBA 的透明度，设置背景色而不是文本的不透明度

#### CSS background-image(背景图片)

```background-image``` 属性指定用作元素背景的图像

* 默认情况下，图像会重复，以覆盖整个元素

* 实例：页面的背景图像可以像这样设置：

```css
<style>
body {
  background-image: url("/i/paper.jpg");
}
</style>
```

还可以为特定元素设置背景图像，例如 <p> 元素

* 实例

```css
p {
  background-image: url("paper.gif");
}
```



**注：图像时，请使用不会干扰文本的图像**

#### CSS background-repeat(背景重复)

##### 1.图像仅在水平方向重复 

* (`background-repeat: repeat-x;`)

* 实例

```css
body {
  background-image: url("gradient_bg.png");
  background-repeat: repeat-x;
}
```

##### 2.垂直重复图像

*  (```background-repeat: repeat-y;```)

##### 3.指定只显示一次背景图像

* (```background-repeat: no-repeat```)

* 实例

```css
body {
  background-image: url("tree.png");
  background-repeat: no-repeat;
}
```

#### CSS background-position(背景图像的位置)

* (```background-position:```)

* 实例

```css
body {
  background-image: url("tree.png");
  background-repeat: no-repeat;
  background-position: right top;
}
```

#### CSS background-attachment(背景附着)

`background-attachment` 属性指定背景图像是应该**滚动还是固定**的（不会随页面的其余部分一起滚动）

* 实例：指定应该固定背景图像：

```css
body {
  background-image: url("tree.png");
  background-repeat: no-repeat;
  background-position: right top;
  background-attachment: fixed;
}
```

* 实例：指定背景图像应随页面的其余部分一起滚动：

```css
body {
  background-image: url("tree.png");
  background-repeat: no-repeat;
  background-position: right top;
  background-attachment: scroll;
}
```

#### CSS background - 简写属性

**缩短代码**，在**一个属性中指定所有背景属性**。它被称为**简写属性**。

简写属性的属性值顺序为：

* background-color
* background-image
* background-repeat
* background-attachment
* background-position

实例

```css
body {
  background: #ffffff url("tree.png") no-repeat right top;
}
```

### 3.CSS 高度和宽度

```height ```和 ```width ```属性用于设置**元素的高度和宽度** **(不包括**、 **内边距、边框或外边距！**它们设置的是**元素的**内边距、边框和外边距内的区域的高度/宽度)

`height` 和 `width` 属性可设置如下值：

* `auto` - 默认。浏览器计算高度和宽度。
* `*length*` - 以 px、cm 等定义高度/宽度。
* `%` - 以包含块的百分比定义高度/宽度。
* `initial` - 将高度/宽度设置为默认值。
* `inherit` - 从其父值继承高度/宽度

实例：设置 <div> 元素的高度和宽度：

```css
div {
  height: 200px;
  width: 50%;
  background-color: powderblue;
}
```

设置 max-width

* `max-width` 属性用于设置元素的最大宽度

* 当浏览器窗口小于元素的宽度（500px）时，会发生之前那个 `<div>` 的问题。然后，浏览器会将水平滚动条添加到页面。
* 使用 `max-width` 能够改善浏览器对小窗口的处理。

```css
div {
  max-width: 500px;
  height: 100px;
  background-color: powderblue;
}
```

# 六、CSS 文本

### 1.文本颜色

`color` 属性用于设置文本的颜色。颜色由以下值指定：

* 颜色名 - 比如 "red"
* 十六进制值 - 比如 "#ff0000"
* RGB 值 - 比如 "rgb(255,0,0)"

实例（定义了 background-color 属性和 color 属性）

```css
body {
  background-color: lightgrey;
  color: blue;
}

h1 {
  color: green;
}
```

### 2.文本对齐

#### 1.对齐方式

text-align 属性用于**设置文本**的**水平对齐方式**(**文本**可以**左对齐**或**右对齐**，或**居中对齐**)

* 实例

```css
h1 {
  text-align: center;
}

h2 {
  text-align: left;
}

h3 {
  text-align: right;
}
```

* 当 `text-align` 属性设置为 **"justify"** 后，将拉伸每一行，以**使每一行具有相等的宽度，并且左右边距是直的**（就像在**杂志**和**报纸**中）

#### 2.文本方向

```direction ```和 ```unicode-bidi ```属性可用于更改元素的文本方向

* 实例

```css
p {
  direction: rtl;
  unicode-bidi: bidi-override;
}
```

```unicode-bidi ```属性单独使用没有效果

#### 3.垂直对齐

`vertical-align` 属性设置元素的垂直对齐方式。

* 实例：演示如何设置文本中图像的垂直对齐方式：

```css
<head>
<style>
img.top {上对齐
  vertical-align: top;
}

img.middle {居中对齐
  vertical-align: middle;
}

img.bottom {下对齐
  vertical-align: bottom;
}
</style>
</head>
<body>

<p>一幅 <img src="/i/logo/w3logo-3.png" alt="W3School" width="180" height="167"> 默认对齐方式的图像。</p><br>

<p>一幅 <img class="top" src="/i/logo/w3logo-3.png" alt="W3School" width="180" height="167"> 上对齐的图像。</p><br>

<p>一幅 <img class="middle" src="/i/logo/w3logo-3.png" alt="W3School" width="180" height="167"> 居中对齐的图像。</p><br>

<p>一幅 <img class="bottom" src="/i/logo/w3logo-3.png" alt="W3School" width="180" height="167"> 下对齐的图像。</p>

</body>
```

### 3.文本装饰

`text-decoration` 属性用于**设置或删除文本装饰**

```css
<head>
<style>
a {
  text-decoration: none;用于从链接上删除下划线
}
h1 {
  text-decoration: overline;上划线
}

h2 {
  text-decoration: line-through;删除线
}

h3 {
  text-decoration: underline;下划线
}
</style>
</head>
<body>

<h1>This is heading 1</h1>
<h2>This is heading 2</h2>
<h3>This is heading 3</h3>

</body>
```

### 4.文本转换

```text-transform ```属性用于指定文本中的大写和小写字母。

* 可用于将**所有内容转换为大写或小写字母**，或将**每个单词**的**首字母大写**

* 实例

```css
p.uppercase {
  text-transform: uppercase;全部大写
}

p.lowercase {
  text-transform: lowercase;全部不大写
}

p.capitalize {
  text-transform: capitalize;首字母大写
}
```

### 5.文字间距：

#### 文字缩进

```text-indent ```属性用于**指定文本第一行的缩进**

* 实例

```css
p {
  text-indent: 50px;
}
```

#### 字母间距

```letter-spacing ```属性用于指定**文本**中**字符之间的间距**

* 实例:增加或减少字符之间的间距：

```css
<head>
<style>
h1 {
  letter-spacing: 3px;
}

h2 {
  letter-spacing: -3px;
}
</style>
</head>
<body>

<h1>This is heading 1</h1>
<h2>This is heading 2</h2>

</body>
```

#### 行高

`line-height` 属性用于指定**行之间的间距**

* 实例

```css
<head>
<style>
p.small {
  line-height: 0.7;
}

p.big {
  line-height: 1.8;
}
</style>
</head>
<body>

<p>
这是有标准行高的段落<br>
大多数浏览器中的默认行高大概是 110% 到 120%。<br>
</p>

<p class="small">
这是行高更小的段落。<br>
这是行高更小的段落。<br>
</p>

<p class="big">
这是行高更大的段落。<br>
这是行高更大的段落。<br>
</p>

</body>
```

#### 字间距

`word-spacing` 属性用于指定文本中**单词之间的间距**

* 实例：增加或减少单词之间的间距：

```css
<head>
<style>
h1 {
  word-spacing: 10px;
}

h2 {
  word-spacing: -5px;
}
</style>
</head>
<body>

<h1>This is heading 1</h1>
<h2>This is heading 2</h2>

</body>
```

#### 空白

`white-space` 属性指定元素**内部空白的处理方式**

* 实例：禁用元素内的文本换行：

```css
p {
  white-space: nowrap;
}
```

### 6.文本阴影

`text-shadow` 属性为**文本**添加**阴影**

* 实例（**水平阴影、垂直阴影、阴影颜色、模糊效果**）

```css
h1 {
  text-shadow: 2px 2px 5px red;
}依次控制水平阴影、垂直阴影、模糊效果、阴影颜色
```

# 七、字体

在 CSS 中，有五个通用字体族：

* **衬线字体**（Serif）- 在每个**字母**的**边缘都有**一个小的**笔触**。
* **无衬线字体**（Sans-serif）- **字体线条简洁**（**没有小笔画**）。
* **等宽字体**（Monospace）- 这里**所有字母**都有**相同**的**固定宽度**。
* **草书字体**（Cursive）- **模仿**了**人类**的**笔迹**。
* **幻想字体**（Fantasy）- 是**装饰性/俏皮**的字体。

### CSS font-family 属性

在 CSS 中，我们使用 font-family 属性规定文本的字体

font-family 属性应**包含多个字体名称**作为**“后备”系统**，以**确保浏览器/操作系统**之间的**最大兼容性**。**以需要的字体开始**，并**以通用系列结束**（如果没有其他可用字体，则让浏览器选择通用系列中的相似字体）。**字体名称**应**以逗号分隔**。

注：字体名称若是多个单词则用引号括起来

### 字体样式

#### 1.斜体文本

`font-style` 属性主要用于指定**斜体文本**

此属性可设置三个值：

- normal - 文字**正常显示**
- italic - 文本以**斜体显示**
- oblique - 文本为**“倾斜”**

实例

```css
p.normal {
  font-style: normal;
}
```

#### 2.字体粗细

`font-weight` 属性指定**字体的粗细**

实例

```css
p.normal {
  font-weight: normal;
}

p.thick {
  font-weight: bold;
}
```

#### 3.字体变体

`font-variant` 属性指定**是否以 small-caps 字体（小型大写字母）显示**文本

ps：在 **small-caps 字体**中，**所有小写字母都将转换为大写字母**。但是，**转换后**的**大写字母的字体大小小于文本中原始大写字母的字体大小**。

实例

```css
p.normal {
  font-variant: normal;
}

p.small {
  font-variant: small-caps;
}
```

### 字体大小

```font-size ```属性**设置文本的大小**,```font-size ```**值**可以是**绝对或相对大小**

#### 1.以像素设置字体大小

使用**像素设置**文本大小可以**完全控制**文本大小

* 实例

```css
h1 {
  font-size: 40px;
}

h2 {
  font-size: 30px;
}
```

ps：如果**使用像素**，仍然可以**使用缩放工具**来**调整整个页面**的**大小**。

#### 2.用 em 设置字体大小

默认大小 1em 为 16px

* 实例

```css
h1 {
  font-size: 2.5em; /* 40px/16=2.5em */
}
```

#### 3.使用百分比和 Em 的组合

* 实例

```css
body {
  font-size: 100%;
}

h1 {
  font-size: 2.5em;
}
```

#### 4.响应式字体大小

使用 `vw` 单位设置文本大小(vw—“视口宽度”)

* 实例

```css
<h1 style="font-size:10vw">Hello World</h1>
```

ps：1vw = 视口宽度的 1％。如果视口为 50 厘米宽，则 1vw 为 0.5 厘米

### 简写属性

font 属性是以下属性的简写属性：

* ```font-style```
* ```font-variant```
* ```font-weight```
* ```font-size/line-height```
* ```font-family```

实例

```css
p.b {
  font: italic small-caps bold 12px/30px Georgia, serif;
}
```

注：```font-size``` 和 ```font-family ```的**值是必需的**。**如果缺少其他值之一**，则会**使用其默认值**。

# 八、CSS 链接

### 1.设置链接样式

链接可以使用**任何 CSS 属性**（例如 `color`、`font-family`、`background` 等）来**设置样式**

根据链接**处于什么状态**来**设置链接的不同样式**

四种链接状态分别是：

```a:link``` - 正常的，未访问的链接
```a:visited``` - 用户访问过的链接
```a:hover``` - 用户将鼠标悬停在链接上时
```a:active``` - 链接被点击时

* 实例

```css
/* 未被访问的链接 */
a:link {
  color: red;
}

/* 已被访问的链接 */
a:visited {
  color: green;
}

/* 将鼠标悬停在链接上 */
a:hover {
  color: hotpink;
}

/* 被选择的链接 */
a:active {
  color: blue;
}
```

### 2.文本装饰

```text-decoration``` 属性主要用于从链接中删除下划线

### 3.背景色

```background-color``` 属性可用于指定链接的背景色

* 实例

```css
a:link {
  background-color: yellow;
}

a:visited {
  background-color: cyan;
}

a:hover {
  background-color: lightgreen;
}

a:active {
  background-color: hotpink;
} 
```

### 4.链接按钮

组合多个 CSS 属性，将链接显示为框/按钮

* 实例

```css
a:link, a:visited {
  background-color: #f44336;
  color: white;
  padding: 14px 25px;
  text-align: center; 
  text-decoration: none;
  display: inline-block;
}

a:hover, a:active {
  background-color: red;
}
```

### 5.多个属性和状态时可以用如下格式

```css
a.one:link {color:#ff0000;}
a.one:visited {color:#0000ff;}
a.one:hover {color:#ffcc00;}
```


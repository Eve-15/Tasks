# <center>Dom树初步了解和学习</center>

# 一、什么是DOM

DOM（Document Object Model）即文档对象模型，是W3C制定的标准接口规范，是一种处理HTML和XML文件的标准API。DOM提供了对整个文档的访问模型，将**文档作为一个树形结构**，树的**每个结点表示了一个HTML标签或标签内的文本项**。DOM树结构精确地描述了HTML文档中标签间的相互关联性。**将HTML或XML文档转化为DOM树的过程称为解析(parse)。** **HTML文档被解析后，转化为DOM树**，**因此对HTML文档的处理可以通过对DOM树的操作实现。**DOM模型不仅**描述了文档的结构**，还**定义了结点对象的行为**，利用**对象的方法和属性**，可以**方便地访问、修改、添加和删除DOM树的结点和内容。**

* 作为对象的 HTML 元素
* 所有 HTML 元素的属性
* 访问所有 HTML 元素的方法
* 所有 HTML 元素的事件

**ps：**

1. API 是 Application Programming Interface 的缩写，中文翻译为“应用程序编程接口”。它是一种定义如何与软件应用程序进行交互和通信的规范。API 允许不同的软件应用程序相互通信并共享数据和功能，从而加速开发过程并提高工作效率。

2. XML是可扩展标记语言（Extensible Markup Language）的缩写。它是一种用于存储和传输数据的标记语言，可以用来描述文档的结构和内容。与HTML不同，XML可以用于创建自定义的标记，以便更好地描述和组织数据。它是一种通用的语言，可以用于各种应用程序和服务之间进行数据交换和存储。

### 几个关键字便于理解

* 元素（element）：文档中的都有标签都是元素，元素可以看成是对象
* 节点（node）：文档中都有的内容都是节点：标签，属性，文本
* 文档（document）：一个页面就是一个文档
* 这三者的关系是：文档包含节点，节点包含元素

# 二、Model 模型

文档（页面）中有一个**根（root）**，这个根标签**包含head标签与body标签**，**head**标签中又**包含meta与title标签**，**body标签中包含div、p、header、main等等标签**，其中**main**下面又**有article、aside等等标签**，**article**标签中又有**其它的标签**等等，**这就组成了树状结构图，也叫DOM树**。这就形成了一个模型。看下图的关系。
![img](https://img-blog.csdnimg.cn/20200604132033120.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaTEyNzMzNTYwNzg=,size_16,color_FFFFFF,t_70#pic_center)

* Object 对象
  “万物皆对象”相信小伙伴们对这5个字有点印象吧。**把所有的事物都当作一个对象**，html文件是一个对象，html文件中的标签也是对象

# 三、DOM的作用

让JavaScript可以对文档中的**标签**、**属性**、**内容**等进行 **访增删改** 操作。

**实例：html内容**

```html
<div>我是div元素</div>
<p id="p">我是p元素</p>
```

* **访**

```html
var div = document.getElementsByTagName('div')
var p = document.getElementById('p')
```

* **增**

```html
// 创建一个a元素
var a = document.createElement('a')
// 添加到body
document.body.append(a)
```

* **删**

```html
// 移除body中的div子节点
document.body.removeChild(div)
```

* **改**

```html
div.innerHTML = '我修改了div的文本内容'
```

# 四、对象的HTML DOM树

![DOM HTML 树](https://www.w3school.com.cn/i/ct_htmltree.gif)

- JavaScript 能改变页面中的所有 HTML 元素
- JavaScript 能改变页面中的所有 HTML 属性
- JavaScript 能改变页面中的所有 CSS 样式
- JavaScript 能删除已有的 HTML 元素和属性
- JavaScript 能添加新的 HTML 元素和属性
- JavaScript 能对页面中所有已有的 HTML 事件作出反应
- JavaScript 能在页面中创建新的 HTML 事件

# 五、自己的看法和理解

在了解dom树的过程中同时了解了一下js，以及HTML、css、js这三种语言相互协同工作的重要性，如果只用html和css做出来的网页可能就很像小报了，缺少行为与交互。同时也让我感受到了js比HTML学习的内容和难度都要高。

在客户端脚本内，document将html和xml翻译解析为dom树，从而更加方便去遍历节点（据之前看网课了解计算机最擅长的方式是一个一个去试，简单的逻辑快速运算）然后通过document.getElementById(id)（是一个DOM方法，它返回具有指定ID的第一个Element对象。如果找不到这样的元素，则返回null。这也是id为什么只能在一个元素中使用的原因）去访问HTML元素，HTML元素通过id属性来定义，用innerHTML写入HTML元素（定义HTML内容）

通过dom则可以轻松定位到想到的标签，而加入id则可以更好的定位，而一切皆对象则可以使js利用dom对象来对dom树进行修改

而onclick属性的值是一个js函数的调用或者代码块，当用户点击该元素时，绑定的函数或代码将被执行。在制作简单网页时应该有用

总之首先将HTML和xml文件解析为dom树，将数据结构化，使每个标签、文本等等都有自己的位置，dom提供了对文档的访问模型，而js和其他编程语言则是访问的工具，再加上id的精准定位从而让用户**动态的修改页面内容**

# 六、问题

在dom树中访问HTML元素时是采取遍历的方式吗？

可以理解为：HTML作为树的骨架，然后通过js为其修饰枝叶吗？


# css笔记

全名： Cascading      Style      Sheets

寓意：     层叠             样式        列表 

内部样式表：style定义在html内部

外部样式表：

## css选择器

作用：用来选择（找到）需要添加样式的位置

常用选择器：标签选择器，（归）类选择器 等

## 背景样式

|      | 属性                  | 属性值                               | 作用                 |
| ---- | --------------------- | ------------------------------------ | -------------------- |
| 1    | background-color      | 颜色值                               | 颜色作为背景颜色     |
| 2    | background-image      | 图片位置                             | 图片作为背景图片     |
| 3    | background-repeat     | repeat、repeat-x repeat-y、no-repeat | 背景图片的重复方向·  |
| 4    | background-attachment | scroll、fixed                        | 背景是否随滚动条滚动 |
| 5    | background-position   | 见详细表格                           | 背景图像的起始位置   |
| 6    | background            | 背景样式的值是复合属性组合           |                      |

| 值                                                           | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| top left<br>top center<br>top right<br>center left<br>center center<br>center right<br>bottom left<br>bottom center<br>bottom right | 如果仅定义一个关键词，那么第二个值将会是“center”             |
| x% y%                                                        | 第一个值是水平位置，第二个值是垂直位置。<br>左上角是0% 0%。右下角是100%100%<br>如果仅规定了一个值，另一个值将是50% |
| xpos ypos                                                    | 第一个值是水平位置，第二个值是垂直位置。<br>左上角是0 0。单位是像素（0px 0px）或任何其他的CSS单位。<br>如果仅规定一个值，另一个值将是50%<br>可以混合使用%和position值。 |

##  外部样式

作用：使网页的表示层与结构层彻底分离

示例：将背景设置，修改为外部样式表

< link rel="stylesheet" type="text/css" href="index.css" >

提示：除了link进行外部样式表的链接，还有其他的方法

### 文本样式

|      | 属性            | 属性值                                  | 作用                     |
| ---- | --------------- | --------------------------------------- | ------------------------ |
| 1    | color           | 表示颜色的内容                          | 设置文本颜色             |
| 2    | direction       | ltr、rtl                                | 文本方向/书写方向        |
| 3    | letter-spacing  | npx(注：n可以是负数)                    | 字符间距                 |
| 4    | line-height     | npx                                     | 行高                     |
| 5    | text-align      | left、right、center、justify            | 文本对齐方式             |
| 6    | text-decoration | none、underline、overline、line-through | 文本的修饰：例如：下划线 |
| 7    | text-shadow     | h-shadow v-shadow blur color            | 文本设置阴影             |
| 8    | text-transform  | none、capitalize、uppercase、lowercase  | 改变字母大小写           |
| 9    | text-indent     | npx、nem                                | 首行缩进                 |

### 字体样式

|      | 属性        | 属性值                   | 作用         |
| ---- | ----------- | ------------------------ | ------------ |
| 1    | font-family | 隶书、仿宋等             | 字体         |
| 2    | font-style  | italic、 oblique、normal | 规定斜体文字 |
| 3    | font-weight | normal、bold、100-900    | 文本的粗细   |
| 4    | font-size   | npx                      | 字体大小     |

### 列表样式

|      | 属性                | 属性值             | 作用                               |
| ---- | ------------------- | ------------------ | ---------------------------------- |
| 1    | list-style-type     | none、disc、circle | 设置列表项目外观                   |
| 2    | list-style-position | inside、outside    | 列表符号的位置                     |
| 3    | list-style-image    | url、none          | 把图像设置为列表项目的标记         |
| 4    | list-style          | 同前面三个         | 简写属性，涵盖以上三个列表样式属性 |

## 伪类

通常情况，超级链接上设置的样式，称为伪类

伪类包含两种：状态伪类和结构性伪类

作用：设置超级链接的4种状态

提示：1、伪类是用在超链接上的效果比较多，但超链接不是伪类。

​			2、伪类是选择器。

### 伪类选择器

|      | 属性      | 作用                           |
| ---- | --------- | ------------------------------ |
| 1    | a:link    | 未访问的链接                   |
| 2    | a:visited | 已访问的链接                   |
| 3    | a:hover   | 鼠标移动到连接上（浮动、悬停） |
| 4    | a:active  | 向被激活的元素添加样式         |
| 5    | ：focus   | 选择拥有键盘输入焦点的元素     |

### （结构性）伪类选择性

|      | 属性              | 作用                                                         |
| ---- | ----------------- | ------------------------------------------------------------ |
| 1    | :first-child      | 选择元素的第一个子元素                                       |
| 2    | :last-child       | 选择某个元素的最后一个子元素                                 |
| 3    | :nth-child()      | 选择某个元素的一个或多个特定的子元素                         |
| 4    | :nth-last-child() | 选择某个元素的一个或多个特定的子元素，从这个元素的最后一个子元素开始算 |
| 5    | :first-of-type    | 选择一个上级元素下的第一个同类子元素                         |

### 伪元素选择器

|      | 属性           | 作用                           |
| ---- | -------------- | ------------------------------ |
| 1    | ::selection    | 选择指定元素中被用户选中的内容 |
| 2    | ::before       | 可以在内容之前插入新内容       |
| 3    | ::after        | 可以在内容之后插入新内容       |
| 4    | ::first-line   | 选择指定选择器的首行           |
| 5    | ::first-letter | 选择文本的第一个字符           |

### CSS其他选择器

|      | 选择器     | 作用                           |
| ---- | ---------- | ------------------------------ |
| 1    | id,*       | 选择指定元素中被用户选中的内容 |
| 2    | 逗号选择器 | 联合选择器                     |
| 3    | 空格选择器 | 子孙（后代）选择器             |
| 4    | >选择器    | 子选择器（不是子孙后代）       |
| 5    | +选择器    | 相邻兄弟选择器                 |
| 6    | []         | 属性选择器                     |

 ## DIV

### DIV样式设置

 #### overflow属性设置

|      | 属性    | 作用                                       |
| ---- | ------- | ------------------------------------------ |
| 1    | visible | 默认值。内容不会被修剪，会呈现在元素框之外 |
| 2    | hidden  | 超出部分被隐藏                             |
| 3    | scroll  | 不论是否需要，都显示滚动条                 |
| 4    | auto    | 按需显示滚动条以便查看其余的内容           |

#### css轮廓outlin

作用：绘制于元素周围的一条线，位于边框边缘的外围，可起到突出元素的作用

示例：outline：：dashed；/*虚线轮廓*/

提示：还有：dotted（点状轮廓）solid（实线）double（双线）等

#### css边框： border-left、border-right、border-top、border-bottom

作用：设置div边框的边线宽度、颜色、虚线、实线等样式css属性

示例：border-bottom：solid

### 盒子模型

width、height、border、margin（外边框）、padding（内边框）；

![image-20220610162955346](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220610162955346.png)

## 居中

1、将文字居中

2、将对象居中

文字居中：就是让自己容器中的元素居中，常作用于文本或图片等内联元素。

对象居中：就是让容器中的自己居中，常作用于块元素，且需配合宽度使用。

## 行级元素

概念：行内元素和其他行内元素都会在一条水平线上排列，都是在同一行的

行级元素有:a标签、label、img、span等

## 块级元素

概念：块级元素在默认情况下会独占一行

块级元素：div、h标签、li、table

### 定位机制

分类：标准文档流、脱离标准文档流（float、position：absolute）

文档流特点：空白折叠现象、高矮不齐，底边对齐、自动换行，一行写满，换行写

脱离标准文档流

#### **float：**			

|      | 属性  |        作用        |
| ---- | ----- | :----------------: |
| 1    | left  |    元素向左浮动    |
| 2    | right |    元素向右浮动    |
| 3    | none  | 默认值。元素不浮动 |

#### float的初衷、包裹、崩坏

初衷：图文混排

崩坏：子元素设置为浮动之后父元素没有指定高度的情况下父元素将没有高度；

包裹：当产生浮动之后，div的宽度会自适应于里面的内容；

### 浮动清除

为什么清除浮动：

* 为了父元素不会出现 “高度崩塌”
* 如果强制规定外层容器的尺寸，则显得就不那么灵活了，高度就不能自动适应了
* 从某个元素开始，不再需要浮动效果了

clear：both、left、right

主流写法：

```css
#clearDiv：：after{
    content:"";/*有内容但不显示*/
    visibility:hidden;/*有内容但不显示*/
    height:0px;
    display:block;/*将content变为块级元素*/
    clear:both;
}
```

IE浏览器的处理加上

```css
#clearDiv：：after{
	zoom:1;
}
```

## css定位

 position : relative 、absolute、 static 、 fixed

​                    相对			绝对		无定位       固定 

### 相对定位

相对定位的偏移参考元素是元素本身，不会使元素脱离文档流。元素的初始位置占据的空间会被保留。

主要代码：position:relative

### 绝对定位

相对于已定位的最近的祖先元素，如果没有已定位的最近的祖先元素，那么它的位置就相对于最初的包含块（如body）

主要代码：position:absolute

# html 笔记

## 标签

p   换段

br   换行不换段

!--这是一个注释--

h标签：定义标题头的六个不同文字大小，依次显示重要性的递减，也就是权重依次降低，越靠近body越好，对于搜索引擎的领略有所帮助

img标签：作用：在浏览器显示图片

 				 示例：![image-20220605174333106](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220605174333106.png)

​				常用属性：src、alt、height、width

### 超文本标签

A标签的target属性

| 标签    | 格式                                  |
| :------ | ------------------------------------- |
| _blank  | 在新打开、未命名的窗口打开链接        |
| _parent | 在父窗口打开链接                      |
| _self   | 在当前窗口打开                        |
| _top    | _top目标将会清除所有被包含的frame框架 |

 **锚点标签**：

定义：《a name="minzi">....</a>

作用：同一个文档中创建指向该锚（位置）的链接;

锚点必须先定义，再使用;

### 无序列表

< ul>< li>......</ li></ ul>

作用：此列项目使用粗体圆点（典型的小黑圆圈）进行标记

提示：列表项内部可以使用段落、换行符、图片、链接以及其他列表等；

### 有序列表

< ol>< li>......</ li></ ol>

作用：列表项目使用数字进行标记

提示：列表项内部可以使用段落、换行符、图片、链接以及其他列表等；

### 表格

table：表格的开始和结束、caption：标题、tr：行的添加、th：标题单元格、td：普通单元格、border：边框、width：设置宽度  tbody、thead、tfoot、

![image-20220606202204864](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220606202204864.png)

作用：用于制作表格

合并行列：colspan、rowspan

作用：将表格内的某些行、列进行合并

### 表格属性

| 属性        | 值                                         | 描述                               |
| ----------- | ------------------------------------------ | ---------------------------------- |
| align       | right<br>left<br>center<br>justify<br>char | 定义在列组合中内容的水平对齐方式。 |
| char        | character                                  | 规定根据哪个字符来对齐列组中的内容 |
| charoff     | number                                     | 规定第一个对齐字符的偏移量         |
| span        | number                                     | 规定列组应该横跨的列数             |
| valign      | top<br>middle<br>bottom<br>baseline        | 定义在列组合中内容的垂直对齐方式   |
| width       | pixels<br>%                                | 规定列组合的宽度                   |
| bgcolor     | npx,n%                                     | 表格宽度                           |
| cellpadding | npx                                        | 内容和边框之间的间距               |
| cellspacing | npx                                        | 单元格之间的间距                   |

| 属性名称 | 属性值              | 作用                 |
| :------: | ------------------- | -------------------- |
|  frame   | void                | 不显示外边框         |
|          | border              | 四周都显示           |
|          | above               | 显示上部的外边框     |
|          | below               | 显示下部的外边框     |
|          | hsides              | 显示上下的外边框     |
|          | lhs                 | 显示左部的外边框     |
|          | rhs                 | 显示右部的外边框     |
|          | vsides              | 显示左右的外边框     |
|  rules   | none                | 内边框将不被显示     |
|          | rows                | 内边框将在行之间显示 |
|          | cols                | 内边框在列之间显示   |
|          | all                 | 内边框将被显示       |
|  align   | left、center、right | 三种水平对齐方式     |
|  valign  | bottom、middle、top | 三种垂直对齐方式     |

### 表单

作用：用于收集用户信息，进行人机交互

包含元素：文本框、单选按钮、列表框、图片框、复选框等这些元素被称为“控件”

#### 控件的常用属性



| 属性       | 作用                             |
| ---------- | -------------------------------- |
| name       | 指定控件的名称，可重复           |
| id         | 指定标签的唯一标识               |
| value      | 输入（收集、设置）控件的值       |
| checked    | 复选框（单选）组默认被选中的项目 |
| selected   | 列表框组默认被选中的项目         |
| src        | 图片框的图片来源                 |
| onclick    | 鼠标单击事件                     |
| disabled   | 禁用该控件                       |
| multiple   | 允许多选（适合普通列表框）       |
| placeholde | 在文本框中加入文字提示           |
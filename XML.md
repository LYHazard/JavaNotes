

# XML

* 全称：E**X**tensible **M**arkup **L**anguage，可拓展标记语言
* 编写XML就是编写**标签**，与HTML非常类似，拓展名.xml
* 良好的人机可读性

## XML与HTML的比较

* XML与HTML非常相似，都是编写标签
* XML没有预定义标签，HTML存在大量预定义标签
* XML重在保存和传输数据，HTML用于显示信息

## XML用途

* Java程序的配置描述文件
* 用于保存程序产生的数据

## XML文档结构

* 第一行必须是XML声明

​	XML声明说明XML文档的基本信息，包括版本号与字符集，写在XML第一行。

* 有且只有一个根节点
* XML标签的书写规则与HTML相同

## XML标签书写规则

* 合法的标签名

​    1、标签名要有意义

​	2、建议使用英文，小写字母，单词之间使用“-”分割

​    3、多级标签之间不要出现重名情况

* 适当的注释和缩进
* 合理使用属性

​	1、标签属性用于描述标签不可或缺的信息

​    2、对标签分组或者为标签设置id时常用属性表示

* 处理特殊字符

  1、标签体中，出现"<"、">"特殊字符，会破坏文档结构

  2、解决方案1：使用实体引用

| 实体引用 | 对应符号 | 说明   |
| -------- | -------- | ------ |
| &lt      | <        | 小于   |
| &gt      | >        | 大于   |
| &amp     | &        | 和号   |
| &apos    | ‘        | 单引号 |
| &quot    | “        | 双引号 |

  3、解决方案2：使用CDATA标签

   * CDATA指的是不应由XML解析器进行解析的文本数据
   * 从"<![CDATA["开始，到"]]"结束

## XML语义约束

* XML文档结构正确，但可能不是有效的。
  * 例如，员工档案XML中决不允许出现“植物品种”标签。XML语义约束就是用于规定XML文档中允许出现哪些元素
* XML语义约束有两种定义方式：DTD与XML Schema

### Document Type Definition

* DTD（Document Type Definition，文档类型定义）是一种简单易用的语义约束方式
* DTD文件的拓展名为.dtd。

​	

#### DTD节点定义

* 利用DTD中的<!ELEMENT>标签，我们可以定义XML文档中允许出现的节点及数量，以hr.xml为例：

```dtd
定义hr节点下只允许出现1个employee子节点
<!ELEMENT hr(employee)>
employee节点下必须包含以下四个节点，且按顺序出现
<!ELEMENT employee(name,age,salary,department)>
定义name标签只能是文本，#PCDATA代表文本元素。
<!ELEMENT name(#PCDATA)>
```

#### DTD定义节点数量

* 如某个子节点需要多次重复出现，则需要在子节点后增加相应的描述符。

```xml-dtd
hr节点下最少出现employee子节点
<!ELEMENT hr(employee+)>
hr节点下可能出现0...n个employee子节点//以及只能出现employee子节点。
<!ELEMENT hr(employee*)>
hr节点下最多出现1个employee子节点
<!ELEMENT hr(employee？)>	
```

* 定义属性用< !ATTLIST  >

```dtd

<!ATTLIST employee no CDATD "">
```



#### XML引用DTD文件	

* 在XML中使用<!DOCTYPE>标签来引用DTD文件

```xml
书写格式
<!DOCTYPE 根节点 SYSTEM "dtd文件路径">
示例
<!DOCTYPE hr SYSTEM "hr.dtd">
```



### XML Schema

* XML Schema比DTD更为复杂，提供了更多功能；
* XML Schema提供了数据类型、格式限定、数据范围等特性；
* XML Schema是W3C标准；
* Schema的文件后缀名是.xsd
* Schema 的应用是在根目录下加上 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"（规定使用这个协议） xsi:noNamespaceSchemaLocation="XX.xsd"（引用具体的xsd文件）
* complexType标签含义是复杂节点，包含子节点时必须使用这个标签
* Schema的根目录是 < schema xmlns="http://www.w3.org/2001/XMLSchema" targetNamespace="">

## DOM文档对象模型

* DOM(Document object Model)定义了访问和操作XML文档的标准方法，DOM把XML文档作为树结构来查看，能够通过DOM树来读写所有元素。

###  DOM4j

* Dom4j是一个易用的、开源的库，用于解析XML。它应用于JAVA平台，具有性能优异、功能强大和极易使用的特点
* Dom4j将XML视为Document对象
* XMl标签被Dom4j定义为Element对象

## XPath路径表达式

* XPath路径表达式是XML文档中查找数据的语言。
* 掌握XPath可以极大的提高在提取数据时的开发效率
* 学习XPath本质就是掌握各种形式表达式的使用技巧



最常用的基本表达式

| 表达式   | 描述                                                     |
| -------- | -------------------------------------------------------- |
| nodename | 选取此节点的所有子节点                                   |
| /        | 从根节点选取                                             |
| //       | 从匹配选择的当前节点选择文档中的节点，而不考虑它们的位置 |
| .        | 选取当前节点                                             |
| ..       | 选取当前节点的父节点                                     |
| @        | 选取属性                                                 |

**XPath基本表达式案例**

| 路径表达式      | 结果                                                         |
| --------------- | ------------------------------------------------------------ |
| bookstore       | 选取bookstore元素的所有子节点                                |
| /bookstore      | 选取根元素bookstore。<br>注释:假如路径起始于正斜杠（/），则此路径始终代表到某元素的绝对路径！ |
| bookstore/book  | 选取属于bookstore的子元素的所有book元素                      |
| //book          | 选取所有book子元素，而不管它们在文档中的位置                 |
| bookstore//book | 选择属于bookstore 元素的后代的所有book元素，而不管它们位于bookstore之下的什么位置 |
| //@lang         | 选取名为lang的所有属性                                       |

**XPath谓语表达式**

| 路径表达式                         | 结果                                                         |
| ---------------------------------- | ------------------------------------------------------------ |
| /bookstore/book[1]                 | 选取属于bookstore子元素的第一个book元素。                    |
| /bookstore/book[last()]            | 选取属于bookstore子元素的最后一个book元素。                  |
| /bookstore/book[last()-1]          | 选取属于bookstore子元素的倒数第二个book元素。                |
| /bookstore/book[position()<3]      | 选取最前面的两个属于bookstore元素的子元素的book元素。        |
| //title[@lang]                     | 选取所有拥有名为lang的属性的title元素                        |
| //title[@lang='eng']               | 选取所有title元素，且这些元素拥有值为eng的lang属性           |
| /bookstore/book[price>35.00]       | 选取bookstore元素的所有book元素，且其中的price元素的值须大于35.00 |
| /bookstore/book[price>35.00]/title | 选取bookstore元素中的book元素的所有title元素，且其中的price元素的值须大于35.00 |

## Jaxen介绍

* Jaxen是一个Java编写的开源的XPath库。这是适应多种不同的对象模型，包括DOM，XOM，dom4j和JDOM。
* Dom4j底层依赖Jaxen实现XPath查询
* Jaxen 下载地址：jaxen.codehaus.org

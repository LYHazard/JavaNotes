# JavaScript

* JavaScript是一种脚本语言
* 什么是动态页面、静态页面。动态页面是带有人机交互功能的页面
* JavaScript不需要安装

## JS调试

alert弹框调试、Console.log控制台输出调试

作用:观察变量值的变化规律，是否符合程序设计的目的

示例：alert(flag);

​			console.log(flag);

提示：先掌握熟练这两种方法，再学习其他调试方法

## 数据类型及其转换

|      | 类型      | 作用                                           |
| ---- | --------- | ---------------------------------------------- |
| 1    | number    | 数字类型，整型浮点型都包括                     |
| 2    | string    | 字符串类型，必须放在单引号或者双引号中         |
| 3    | boolean   | 布尔类型，只有true和false两种值                |
| 4    | undefined | 未定义，一般指的是已经声明，但是没有赋值的变量 |
| 5    | null      | 空对象类型，var a = null,和var a=" " 有区别    |

特殊类型

|      | 类型   | 作用                                                         |
| ---- | ------ | ------------------------------------------------------------ |
| 1    | object | 对象类型，在js常见的有window、document、array等              |
| 2    | NaN    | 是Number的一种特殊类型，isNaN()，如果是数字返回false，不是返回true |

类型转换 parseInt() parseFloat() Number() Boolean()

* 需要转换之前注意先进行NaN检测；
* 最好是使用Number()来进行转换；
* "012316.31n352"这类字符Number()不能进行转换所有Number()是比较安全的；

作用 ：强制类型转换、隐式类型转换



```javascript
示例：function test1(){
    console.log("start...");
    var x="a123";
    var flag = isNaN("123");
    var n=parseInt(x);
    console.log("n==="+n);
    console.log("flag==="+flag)
}
```

## 运算符优先级

| 顺序 | 符号            | 描述         |
| ---- | --------------- | ------------ |
| 1    | ()              | 小括号       |
| 2    | ++、--          | 自加、自减   |
| 3    | *  /  %         | 乘  除  取模 |
| 4    | +    -          | 加  减       |
| 5    | <   <=   >   >= | 逻辑运算     |
| 6    | ==   ！=        | 等于  不等于 |
| 7    | &&              | 逻辑与       |
| 8    | \|\|            | 逻辑或       |
| 9    | ?:              | 三目运算符   |
| 10   | =               | 赋值         |

## 内置函数

 ### 字符函数

| 1    | str.substr(起始位置,长度)                     | 截取字符长度                     |
| ---- | --------------------------------------------- | -------------------------------- |
| 2    | str.substring(起始位置，结束位置)             | 截取字符长度                     |
| 3    | str.charAt(第几位数字)                        | 截取具体字符                     |
| 4    | str.length                                    | 获取字符长度                     |
| 5    | str.indexOf(需要查找的字符，查找的初始位置)   | 获取需要查找的字符的位置         |
| 6    | str.split("符号")                             | 以符号来分割字符串存到数组中     |
| 7    | str.concat("内容"，“内容”，“内容”)            | 在源字符串或数组的基础上加上内容 |
| 8    | str.replace("需要替换的内容"，“替换成的内容”) | 将**第一个**符合的内容进行替换   |

### 日期函数

| 1    | Date对象      | var day = new Date();可指定时间如new Date（“2022-6-12”） |
| ---- | ------------- | -------------------------------------------------------- |
| 2    | getDate()     | 获取天                                                   |
| 3    | getMonth      | 获取月（从零开始）                                       |
| 4    | getFullYear() | 获取年                                                   |
| 5    | getHours()    | 获取小时                                                 |
| 6    | gerMinutes()  | 获取分钟                                                 |
| 7    | getSeconds()  | 获取秒                                                   |
| 8    | getTime()     | *获取毫秒数/换算成天数（24×3600×1000）                   |

```javascript
将时间组合成如：2022-1-1 的日期格式
function fun_FmtDate(){
	var d1=new Date();
	var year,month,day,hour,minute,second;
    
    year = d1.getFullYear();
    month = d1.getMonth()+1;
    day = d1.getDate();
    hour = d1.getHours();
    minute = d1.getMinutes();
    second = d1.getSeconds();
	time = year+"-"+month+"-"+day+"-"+hour+":"+minute+":"+second;
    return time;
}
```

## 数学函数

| 1    | Math.round()      | 四舍五入取整         |
| ---- | ----------------- | -------------------- |
| 2    | num.toFixed(位数) | 四舍五入保留几位小数 |
| 3    | Math.min()        | 求最小值             |
| 4    | Math.max()        | 求最大值             |
| 5    | Math.abs()        | 求绝对值             |

## 数组

* 声明或创建一个不指定长度的数组，又称实例化创建：

​       var arrayObj = new Array();

* 声明或创建一个数组并指定长度的数组：

​	 var arrayObj = new Array(5);

* 声明或创建一个带有默认值的数组：

​	var arrayObj  = new Array(2,4,"a","y",8);

* 创建一个数组并赋值的简写，又称隐式创建数据

​	var arrayObj = [2,4,"a","y",8];

## JS对表单元素进行设置

**什么是表单**:表单的主要作用是在客户端接收用户的信息，然后将数据递交给后台的程序来操控这些数据

JS做什么：设置或获取各种表单元素的值

示例：利用js给列表框等表单元素初始化

## 事件

什么是事件：事件是指被程序发现的行为或发生的事情，而且它可能会被程序处理；

特点：js的事件，都是以on开头，有onclick、onchange、onload...

鼠标事件：onclick、ondblclick、onmouseover、onmouseout、onmousedown....

键盘事件：onkeydown、onkeyup、keypress...

表单事件：onfoucs、onsubmit、onblur、onchange....

##  Document Object Model

DOM:将文档（页面）表现为结构化的表示方法，**使每一个页面元素都是可操控**，DOM将网页和脚本以及其他的编程语言联系起来了

特点：利用js控制页面中的所有元素，使页面更加“聪明”；

分类：元素节点、属性节点、文本节点

常用DOM操作

|      | 方法                   | 描述                                         |
| ---- | ---------------------- | -------------------------------------------- |
| 1    | getElementById         | 返回带有指定ID的元素                         |
| 2    | getElementByTagName    | 返回包含带有指定标签名称的所有元素的节点列表 |
| 3    | getElementsByClassName | 返回包含带有指定类名的所有元素的节点列表     |
| 4    | getElemensByName       | 获取相同名称的元素的节点列表                 |


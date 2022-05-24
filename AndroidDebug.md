# Android学习笔记

## 2022.3.13  

### 1.Contentprovider接收端无法访问的问题

​	需要在接收端AndroidManifest中添加权限

```
<uses-permission android:name="exampleProvider._READ_PERMISSION" />
<uses-permission android:name="exampleProvider._WRITE_PERMISSION" />
```

## 2022.3.22 

### 1.Apache 无法访问htdocs中的xml文件问题

需要配置apache的文件访问路径

![image-20220322213126459](C:\Users\22859\AppData\Roaming\Typora\typora-user-images\image-20220322213126459.png)

注意路径分割用的是"/"

### 2.配置允许我们以明文的方式在网络上传输数据而HTTP使用的就是明文传输方式

```xml
<?xml version="1.0" encoding="utf-8"?>
<network-security-config>
<base-config cleartextTrafficPermitted="true">
<trust-anchors>
<certificates src="system" />
</trust-anchors>
</base-config>
</network-security-config>


```

## 2022.3.23

### 1.但是前一天晚上可以访问，第二天就出现Failed to connect to /10.0.2.2:80的问题

分析原因可能是第二天重新联网后被分配的IP地址发生变化，模拟器原来分配的地址无法访问到网址，擦除数据即可；

### 2.引入各种网络库的代码

1）okhttp：implementation 'com.squareup.okhttp3:okhttp:4.9.3'

2）gson：implementation 'com.google.code.gson:gson:2.8.5'

3）retrofitTest: implementation 'com.squareup.retrofit2:retrofit:2.6.1'
							implementation 'com.squareup.retrofit2:converter-gson:2.6.1'

因此添加上述第一条依赖会自动将Retrofit、OkHttp和Okio这几个库一起下载，我们无须再手动引入OkHttp库。另外，Retrofit还会将服务器返回的JSON数据自动解析成对象，因此上述第二条依赖就是一个Retrofit的转换库，它是借助GSON来解析JSON数据的，所以会自动将GSON库一起下载下来，这样我们也不用手动引入GSON库了。

### 3.socket failed: EPERM (Operation not permitted)

没打开网络授权权限；

### 4.协程的依赖库

```kotlin
implementation "org.jetbrains.kotlinx:kotlinx-coroutines-core:1.1.1"
implementation "org.jetbrains.kotlinx:kotlinx-coroutines-android:1.1.1"
```

### 5.协程作用域创建方法

GlobalScope.launch、runBlocking、launch、coroutineScope这几种作用域构建器，它们都可以用于创建一个新的协程作用域。不过
GlobalScope.launch和runBlocking函数是可以在任意地方调用的，coroutineScope函数可以在协程作用域或挂起函数中调用，而launch函数只能在协程作用域中调用。

## 2022.3.28

### 1.Github

将项目push时遇到问题，因为GitHub的默认主支名称由原来的master改为了main；


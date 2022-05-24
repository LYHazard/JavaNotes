# Android学习笔记

## 静态方法

​	静态方法再某些编程语言里面又叫作类方法，指的是那种不需要创建实例就能调用的方法；

```java
JAVA：public class Util{
  
    public static void doAction(){
        System.out.println("do action");
    }
}
```

```kotlin
Kotlin:object Util{
    
    fun doAction(){
        println("do action")
    }
}
```

​	虽然这里的 doAction()并不是静态方法，但是仍然可以使用Util.doAction()的方法来调用，这就是单例类的便捷性；

   如果只希望让类中的某一个方法变成静态方法的调用方式，就可以使用companion object，示例如下：

```kotlin
class Util{

    fun doAction1(){
        println("do action1")
    }
    
    companion object{
        
        fun doAction2(){
            println("do action2")
        }
    }
}
```

​	doAction2()方法其实也并不是静态方法，companion object这个关键字实际上会在Util类的内部创建一个伴生类，而doAction2()方法就是定义在这个伴生类里面的实例方法。只是Kotlin会保证Util类始终只会存在一个伴生类对象，因此调用Util.doAction2()方法实际上就是调用了Util类中伴生对象的doAction2()方法。

​	如果需要真正意义上的静态方法，Kotlin仍然提供了两种方式：注解和顶层方法

注解：

前面使用的单例类和companion object都只是在语法的形式上模仿了静态方法的调用方式，实际上它们都不是真正的静态方法。因此如果你在Java代码中以静态方法的形式去调用的话，你会发现这些方法并不存在。而如果我们给单例类或companion object中的方法加上**@JvmStatic**注解，那么Kotlin编译器就会将这些方法编译成真正的静态方法，如下所示：

```kotlin
class Util{
    fun doAction1(){
        println("do action1")
    }
    
    companion object{
        
        @JvmStatic
        fun doAction2(){
            println("do action2")
        }
    }
}
```

@JvmStatic注解只能加在单例类或companion object中的方法上，如果加在普通方法上就会报错。

顶层方法：顶层方法指的是那些没有定义在任何类中的方法；
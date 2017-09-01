# 异常
  >异常就是程序在运行时出现的不正常情况;

  >我们的写的程序不可能一帆风顺,若异常产生,却没进行正确的处理。则可能导致程序的中断,造成损失,所以我们在开发中要考虑到各种异常的发生,并对其作出正确的处理,确保程序的正常执行。

## 异常体系

  >Throwable
    >>Error
      >>>通常指JVM出现重大问题如：运行的类不存在或者内存溢出等。
不需要编写针对代码对其处理，程序无法处理。

  >Exception
    >>在运行时运行出现的一些情况，可以通过try,catch,finally处理

## 程序

```
  public class Demo {
	public static void main(String[] args){
		System.out.println("begin");
		divide(17/0);
		System.out.println("ending");
	}
	publc static void divide(int a,int b){
		int c= a/b;
	}
}
```

一旦出现异常，程序会立即终止

## 异常五个关键字

  try ,catch,finally throw, throws

  >捕获异常：先捕获小异常再捕获大异常。

  >程序是调出来的，不是写出来的；多测试是程序员的必修课

## 异常处理格式

```
  try{
		//可能出异常的代码
} catch(异常类  对象){
		//处理该异常类型的语句
}
[finally] {
		//一定会执行的代码
		//catch块使用System.exit(1);除外
}

```

## Throwable中的方法
  >String getMessage()

    1.获取异常信息，返回字符串。

  >String toString()

    2.获取异常类名和异常信息，返回字符串。

  >void printStackTrace()

    3.打印异常在堆栈中的跟踪信息;

## 多异常处理格式

```
  try{
		//可能出异常的代码
} catch(异常类A  对象){
		//处理异常类型A的语句
}catch(异常类B  对象){
		//处理异常类型B的语句
}.....
[finally] {
		//一定会执行的代码
		//catch块使用System.exit(1);除外
}

```

## 异常分类

1.编译时被检查异常; 	---> Checked异常

  >在程序中必须使用try...catch处理；

2.编译时不被检测的异常;	---> Runtime异常

  >可以不使用try...catch处理，但一旦出现异常就将由JVM处理。

## 异常之Runtime

RuntimeException(运行时异常)是指因设计或实现方式不当而导致的问题.

>说白了,就是程序员造成的,程序员小心谨慎是完全可以避免的异常.比如,事先判断对象是否为null就可以避免NullPointerException异常,事先检查除数不为0就可以避免ArithmeticException异常;

特点:

>这种异常Java编译器不会检查它,也就说程序中出现这类异常的时候,即使不处理也没有问题,但是一旦出现异常,程序将异常终止,若采用异常处理,则会被相应的程序执行处理.

## 异常之Checked

除了RuntimeException以及子类,其他的Exception及其子类都是受检查异常,我们也可以称为非RuntimeException异常.
特点:

>Java编译器会检查它,也就说程序中一旦出现这类异常,要么是没有try-catch语句捕获,或throws语句没有声明抛出它,编译就不会通过,也就说这种异常,程序要求必须处理.

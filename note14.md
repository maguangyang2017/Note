# 异常

## 方法复写——异常
      1.子类方法中声明抛出的异常类型是父类方法声明抛出异常类型的子类或相同类；
>也就是说：子类方法不能抛出新的异常类；

      2.子类方法可以同时声明抛出多个父类方法声明抛出异常类的子类
```
  class Super{
     public void show() throws IOException{}
}
class Sub extends Super{
    public void show() throws 	FileNotFoundException,IOException,IllegalAccessException{}
}

```

## 方法覆写原则 '一同两小一大'

1.子类中方法与父类方法有相同的返回值类型；

  >子类声明返回的类型也可以是父类声明返回类型的子类；

2.子类中方法与父类方法有相同的方法签名

3.子类中方法的访问权限不能小于父类方法的访问权限

4.子类方法不能抛出新的异常类型

5.子类方法可以同时声明抛出多个父类方法声明抛出异常类的子类(RuntimeException例外)

## throw

自行抛出一个异常对象，抛出异常类的对象

    1.若throw抛出的是Runtime异常

      *程序可以显示使用try...catch来捕获并处理，也可以不管，直接交给方法调用者处理；

    2.若throw抛出Checked异常

      *要么放在try里自己处理，要么放在一个throws声明的方法里面，交给调用者处理。

```
  public static void main(String[] args) {
		try {
		      fn1(1);
		} catch (Exception e) { e.printStackTrace(); }
		fn2(2);
	}
	public static void fn1(int a) throws Exception{
		if(a >0) { throw new Exception("fn1 -- a值不合法"); }
	}
	public static void fn2(int a) {
		if(a >0) { throw new RuntimeException("a值不合法"); }
	}


```

## throws与throw的区别

>thorws用在方法上，后面跟异常类名,可以是多个异常类

>throw用在方法内，后面跟异常对象,只能是一个


## finally

异常的统一出口：

1.不管try块程序是否异常，也不管哪个catch执行，finally块总会执行

>try语句块或会执行的catch语句块使用了JVM系统退出语句例外;//System.exit(1);

2.try块必须和 catch块或和finally同在，不能单独存在，二者必须出现一个。

3.不要在finally中使用return 或throw语句，否则将会导致try、catch中的return或throw失效。


## 自定义异常

自定义类继承Exception或者其子类。

1.使用自定义异常：

>通过构造方法指定具体的异常原因。

>通过throw将自定义异常抛出,交给调用者处理。

```
class MyException extends Exception{
    public MyException (String message){
	 super(message);
    }
    public MyException (){}
}

```

## throw和catch同时使用

当异常出现在当前方法中,程序只对异常进行部分处理,还有一些处理需要在方法的调用者中才能处理完成,此时还应该再次抛出异常,这样就可以让方法的调用者也能捕获到异常;

```
public static void buy(String price) throws Exception {
	try {
		if(price != null)
			Double.parseDouble(price);
	} catch (Exception e) {
		e.printStackTrace();
		throw new Exception("价格不能只能是数字组成");
	}
}
public static void main(String[] args)  {
	try {
		buy(null);
	} catch (Exception e) {
		System.out.println(e.getMessage());
	}
}

```

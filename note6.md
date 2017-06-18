1. 作业：人       手机     卡     发短信
2. Interger    interger=0//自动装箱
-128    ——     127；
● 设计模式（23种）
    ○ 享元模式；
    ○ Singleton模式   （单例模式）
3. Interger    interger1=0
4. System.out.println( interger1== interger);
5. Interger  i = Interger(1);创建包装类对象
    a. i=10;自动装箱
    b. int i1= i.intValue();包装类转换成基本数据类型
    c. float i2= i.floatValue();
6. 字符串-基本数据类型转换
    a. string num = "333"
    b. int i4 = Interger.perseint(num);
    c. System.out.println( i4);
7. 基本数据类型转换成String
    a. int i=10;
    b. String   s = i+""+i;
    c. String  ss = String.valueof(f);
    d. String  sss = new String(f+"");
8.
1. 静态块 >构造块>构造方法
2. 单例模式类型
```
    懒汉

      class Singleton{
      private static Singleton instance = null;
      public static Singleton getInstance(){// 将instance传递到外部去
        if(instance == null){
          instance = new Singleton();
        }
        return instance;
      }
      private Singleton(){}
}

     饿汉
       class Singleton
{
      ///在内部准备好一个对象
      private static Singleton instance = new 	Singleton();

      public static Singleton getInstance(){
        return instance;
      }
      private Singleton(){}

      public void show(){
        System.out.println("Singleton");
      }
}
```
3. 普通代码块
```
    a. ...main.....{
      {
          int x = 1;
           System.out.println("普通代码块" + x);
  }
     int x = 99;
      System.out.println("代码块之外" + x);
}
```
1. 构造代码块
```
    a. public class Demo {
      {
     System.out.println("我是构造代码块");
     }
  public Demo(){
    System.out.println("我是构造方法");
  }
  public static void main(String[] args) {
 Demo d1  = new Demo();
     Demo d2  = new Demo();
     }
}
```
1. 静态代码块
```
    a. public class Demo {
  {
    System.out.println("我是构造代码块");
      }
      public Demo(){
    System.out.println("我是构造方法");
      }
     static {
    System.out.println("我是静态代码块");
     }
      public static void main(String[] args) {
    System.out.println("Main");
    new Demo();
    new Demo();
    }
}
```
● enum实现单例模式

● final关键字

    ○ final可以修饰类,方法,变量。
    ○ final修饰类不可以被继承，但是可以继承其他类。  
    ○ final修饰的方法不可以被覆盖,但可以覆盖父类方法。
    ○ final修饰的变量称为常量，这些变量只能赋值一次。
    ○ 内部类在局部时，只可以访问被final修饰的局部变量。

        ■ final修饰的引用类型变量,表示该变量的引用不能变,而不是该变量的值不能变;

● 抽象类abstract 关键字

    ○ 通过abstract关键字来修饰的类称为抽象类；
    ○ 可以定义被abstract修饰的抽象方法
    ○ 抽象方法只有返回类型和方法签名，没有方法体。
    ○ 抽象类可以含有普通方法
    ○ 抽象类不能创建实例对象（不能new）
    ○ 需要子类覆盖掉所有的抽象方法后才可以创建子类对象，否则子类也必须作为抽象类
    ○ 列举常见的几个抽象类：
    ○ 流的四个基本父类
    ○ InputStream，OutputStream，Reader，Writer

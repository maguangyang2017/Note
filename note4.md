● 把一组或多组事务相同的特性的集合的描述-------->类

● 类当中有很多成员

● 类------->抽象化

● 类当中的个体才能进行实际的操作

● 花木兰  ————英雄类当中的个体

● 个体称之为<——>对象（类当中的一个个体）
<抽象画过程

● 类<=======>对象
具象化过程>
```
     public class Student {
      //声明类的属性
      String name;    //姓名属性
      int age;		//年龄属性
      char sex;		//性别属性
      //构造器————实例化的时候自己调用的
      //构造器名字必须和类名一致，并且没有返回值
      //实例化对象时直接调用数据
      public Student (){
      System.out.println(“我被调用了”);
      }
      //声明类的动作属性
      public void eat (){
      System.out.println("eating");
      }
      public void study (){
      System.out.println("study");
      }
      public void playgame (){
      System.out.println("playgame");
      }
      }
```
```
public class Student {
//属性
String[] zhuangbei;
int type;//1----射手
String pf;皮肤
int heat;伤害
//方法
public boolean jineng(){
System.out.println("闪现");
ruturn true;
}
public int move(){
System.out.println("move");
ruturn 0;
}
}
```

● 书写时要加注释！！！！！！！

● //具象化过程

```
public class main{
public static void main(String[] arg){
String[]  ss = new string;
ss[] = new string();
//产生对象  Studeng类的对象
Studeng studeng1 = new Student();
student1.name = "xusongjun";
想表示两个或多个对象，这能通过new创建
Studeng studeng2 = new Student();
student2.name = "dingyi";
}
}
```

● 面向过程：强调的是功能行为,一种过程,先干啥,再干啥;

● 面向对象：将功能封装到对象里，强调的是具备某功能的对象;

● 面向对象的三个特征：

  封装(Encapsulation);
  继承(Inheritance);
  多态(Polymorphism);

● 声明类级别的属性

    ○ static int student；

● static关键字

    ○ 特点：
      随着类的加载而加载
      优先于对象存在
      被所有对象所共享
      可以直接被类名调用

● 使用注意：
    静态方法只能访问静态成员
    但是非静态成员可以访问静态成员;
    静态方法中不可以使用this，super关键字
    主方法（main）是静态的

● 被static方法修饰的方法叫静态方法

● 匿名对象

    ○ 对方法或字段只进行一次调用时；
        new Car().show();

● this 当前类本身

    ○ this.name = name；

● public class Teacher extends(继承) person {

● }

● 泛化操作——将student 和 teacher 共同的部分抽离出来preson

    ○   person 父类——teacher和student为子类
● 特化——从父类当中，有自己的特殊的部分

● 三个修饰符

    ○ public 功能 任何地方
    ○ provate 类的内部
    ○ protected 子类当中，不能在类的外部

● object是所有类的父类
● 继承是一般到特殊的关系

    ○ 好处：提高代码复用性，提高效率

● 方法的覆写——相当于拓展父类的成员。

● super（调用父级）.eat——调用父类的属性

● 调用父类构造器 super （name,sex,age）必须写在第一行

● 强制类型转换  （只存在继承之间）

    ○ if(dog instanceof erha){ ..((erha)dog).biaoqing();.}
    ○   instanceof 判断是不是这个类型

● 判断复写必杀技:子类方法前加上@Override能编译通过,表明是方法的覆写。
No.区别点重载（overload）覆写（override）1判断
规则两同一不同一同两小一大2权限没有权限要求被覆写的方法不能拥有比父类更严格的权限3范围发生在一个类之中发生在继承关系中4术语overloadoverride5多态编译时多态运行时多态

● this()必须写在第一行；

1. ls 查看文件
2. 禁止一个源文件有两个类
3. 在一个源文件中只能有一个类文件被public修饰
4. 不提倡在源文件中出现多个类（匿名类）
5. 在一个源文件中如果有多个类的定义，那么编译完成后会出现多个字节码
6. 类名第一个字母必须大写
7. 语句要写在方法体中
8. 整形默认值  0
9. 定义 static
10. 同一个作用域只能定义一个
11. java使用unicode 编码
12. char[] cs = new char[10]
13. int[] as = now int[10]
14. 输入数字
    a. import java.util Scanner
15. Scanner sc new Scanner (system.in)
16. int sca = sc.nextInt();
17. java的语法格式
    a. 代码都定义在类中,类由class来定义，区分 public class  和  class
    b. 代码严格区分大小写,如main 和 Main  是不一样的
    c. Java中的标识符与关键字
    d. 注释
18. main方法的作用：
    a. 程序的入口
    b. 保证程序的独立运行
    c. 被JVM调用
19. 注释
    a. 单行注释      //
        i. //后到本行结束的所有字符会被编译器忽略
    b. 多行注释     /* */
        i. /*  */之间的所有字符会被编译器忽略
    c. 文档注释     /** */
        i. 在/**  */之间的所有字符会被编译器忽略,java特有的(用于生成文档)
    d. 多行和文档注释都不能嵌套使用
20. java分隔符
    a. 分号 ；
        i. 语句的分割,表示一句话结束,好比咱们使用的句号；
    b. 花括号 {}
        i. 表示一个代码块，是一个整体，花括号要一起使用；
    c. 方括号 []
        i. 定义数组和访问数组元素时使用；
    d. 圆括号 ()
        i. 使用很广泛，具体用到细讲；
    e. 圆点  .
        i. 类/对象 访问它的成员(字段，方法)时使用等。
    f. 空格
        i. 分割一条语句的不同部分，空格的次数不限制
21. 关键字
abstract抽象doimplement实线privatethisbooleandouble双import导入protectedthrowbreak清除elseinstanceofpublicthrowsbyteextendsintreturntransientcasefalseinterfaceshorttruecatchfinallongstatic静态trycharfianllynativestrictfpvoidclassfloatnewsupervolatilecontinuefornullswitchwhiledefaultifpackageenumsynchronizedassert
22. 标识符
    a. 由字母、数字、下划线、$组成，不能以数字开头(注意:此处的字母还可以是中文,日文等)
    b. 大小写敏感
    c. 不得使用java中的关键字和保留字
    d. 别用Java API里面的类名作为自己的类名
23. 局部变量
    a. 局部变量使用前必须初始化值;
    b. 局部变量没有默认初始化值;
    c. 局部变量的作用域是从定义开始到定义它的代码块结束;
24. 成员变量(在方法体外,类体内声明的变量，又称字段(Field)或全局变量)
    a. 成员变量的作用域是整个类中;
25. 数据类型

基本分数据类型     栈区  
引用数据类型   将引用 存放在栈区
将内容存放在堆区
26. String 字符串型
27. 基本数据类型
    a. 布尔型： boolean
    b. 字符型： char
    c. 整数型： byte、short、int 、long
    d. 浮点数型：float、double
序号数据类型大小/位(B)数据范围1byte8[-128,127]2short16[-215,215-1]3int32[-231,231-1]4long64[-263,263-1]5char16[0,216-1]6float32[-3.4E38(-3.4*1038)，3.4E38(-1.7*1030];7double64[-1.7E308(-1.7*10308)，1.7E308(-1.7*10308];8boolean1true / false
28. 整形默认 int
29. 浮点型默认 double
30. 当精度比较大相比较小的负值时，损失精度
    a. long===>int
    b. double====>float
31. 两个数值形相加，最终结果数据类型较大的
    a. 3+3.14====>double
32. 字符型与整形相加，最终结果是整形
    a. ‘a'+1===66
33. 字符串和整形相加
    a. "这是"+1=======这是1
    b. "这是"+"1"=======这是1
    c. 3+4+"这是"+"2"=====7这是2
34. 输入需创建scanner
    a. Scanner sc = new Scanner（scanner.in）;
    b. 接受
        i. int a= sc.nextInt();

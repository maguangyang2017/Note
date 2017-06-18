1. instanceceof   检查是否是位的对象
2. 方法

     public static int equalslarger （int a， int b）

     修饰符 返回值类型 方法名（参数列表）{
         方法体
         [return 0]
         }
3. 方法的签名
     判别方法唯一（方法名+参数列表（顺序，个数，类型））
     方法名参数列表(参数的顺序也是关键)
4. 方法的重载
     两同
         同一个类
         方法名相同
     一不同
         参数列表不同（顺序，个数，类型）
            1. (int add (int a, int b){})
            2. (int add (int a, int b){})
5. 数组声明
     int [][] a = new int [6][4]
     a 如何存放 数组第一个元素的地址
ppt   冒泡 快速  选择    二分查找

6. 三个核心接口
     collection：存放的是一个对象，每次存放单个对象。
     map：每次存放一对值。key——value
     lterator:输出接口，只要是集合都要去使用lterator输出
7. c.remove删除指定元素
8. c.clear 删除所有元素
9. calendar 日历
10. 创建一个类将数组成倍增加
     private String [] arr
     public testarr (String[] arr){
         this.arr = arr;
      }
     public void add(String s){
         index+=1;
         arr[index] = 5;
         if(index>arr.length){
             String[] arr2 = new String[index*2];
             arr = arr2
         }
     }
     public String get(int index){
         return arr[index];
     }
11. List <String>list = new ArrayList<string>();----强制添加string型
     list.add("沙包");
  list.add("豆包");
System.out.println(list.get(0));
Iterator iterator = newlist.iterator();

12. student student = (student)o;
13. hashCode和equlas区别****
14. 定制排序 使用comparator*****
15. map 添加删除查找遍历
16. 倒叙输出***
17. java IO
18. 成绩相等比年龄****

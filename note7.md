1. 集合的创建
    a. 添加add
    b. 查找  get
    c. 删除remove
    d. 遍历for 迭代器
    e. 清空clear
2. 特性：什么时候用什么类型
3. 连表结构
4. linked 快速查找用
5. map<String ,String> maps = new HashMap <String ,String>();

     添加 put

     获取 maps.get（）

     删除maps.remove

     遍历
     set keys = map.keySet（）；遍历key 用keyset
        Interatoe interator = keys.interator;
        while(interator,hasNext){
          String key = (string)interator.next();
          Sstem.out.println("key is"+key);
             }
6. map当中数据比较大
     for（String s:keys）｛

     ｝
7. Porperties pps = System.getproperties();
8. pps.list(System.out);
9. 流

     流是一组有顺序的，有起点和终点的字节集合，是对数据传输的总称或抽象。即数据在两设备间的传输称为流，流的本质是数据传输，根据数据传输特性将流抽象为各种类，方便更直观的进行数据操作
10. file（指文件也指文件夹）文件类
    a. filenameFilter 文件过滤器
    b. RandomAccessFile 随机访问文件
11. java.io.file 文件本身有关的操作类
12. public boolean delect 删除文件
13. mkdir 创建目录
14. list 列出file 所有子文件名
15. 程序保存数据——写出去 输出
16. 程序读取数据——读进来 输入

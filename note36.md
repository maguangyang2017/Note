overflow 溢位：

即：对页面的内容超出了我们固定的一个宽度和高度控制

overflow：hidden  溢位隐藏

意思是把超出内容隐藏。   经常用。

同时还经常用来解决一些页面的问题。如：页面高度定义成auto(自动)以后，背景不下来。

box-shadow:  图层阴影（盒子阴影）

box-shadow:1px 1px 3px #888; 其属性的意思等同于：text-shadow

background:url(../images/bodyb.jpg)  fixed  center  top;  固定背景图片

fixed  固定

li的宽和高不要忘了定义

3）鼠标经过之前不要忘了定义display:none;(也就是让整个ul不显示的意思)
4）.l1:hover .n2{ display:block;}
       意思为，鼠标经过l1时，n2 显示为块，也就是n2显示的意思。
### 圆角

border-radius  描边半径的意思
border-radius:3px 1px 6px 10px;
后面跟四个属性值，分别代表：上   右    下   左，四个角的圆角度数

 * border-top-left-radius
 * border-top-right-radius
 * border-bottom-right-radius
 * border-bottom-left-radius
 * box-shadow:1px 1px 3px #888; 其属性的意思等同于：text-shadow
 * background:url(../images/bodyb.jpg)  fixed  center  top;  固定背景图片
 * fixed  固定

#### 渐变和圆角

backgroud:linear-gradient()

linear-gradient(起点，开始颜色，结束颜色);

　　起点：top，right，bottom，left，top left，top right， bottom left，bottom right

圆角效果：

border-radius:20px 10px 5px 0;      //顺时针四个角的圆角值；IE6、IE7、IE8不支持圆角效果；

正圆：border-radius:50%;  
阴影效果：
box-shadow:3px 3px 2px #CCC;    x偏移，y偏移，扩散值， 颜色值


登陆数据库：

mysql –uroot –p
查看数据库

show databases;
drop database dname；
使用选择数据库

use mysql
show tables;
select * from tname;
show create table tname;

```
create table tname(
	字段名  数据类型   约束
	。
	。
	。
)
```
库->表->字段（列）

对库的操作：

增加
create database 名字

删除
drop database 名字

查询
show databases;

SELECT * from student1 where id=2；
为了不让两条数据出现重复：
增加一列编号：
并且让编号有规律自增


把编号列的数据称为主键
保证数据不会出现重复
一般情况下主键是保持自增的。

如果一个表 当中存在另一个表的主键，我们就吧这个列称为外键。
解决了大数据重复的数据冗余问题，

有外键的情况下，两张表就存在了关系，
关系型数据库 MYSQL
非关系型数据库 NOSQL

对库的操作：

增加
create database 名字

删除
drop database 名字

查询
show databases;

对表的操作：
```
CREATE TABLE student1(
  sname varchar(20),
  sage  INT(3),
  ssex  char(5)
) ENGINE=InnoDB DEFAULT CHARSET=utf8
```
-- 插入数据
```
INSERT INTO student1(`sname`,`sage`)
VALUES('东坡2',111);
```
-- 查询student1
```
select * from student1;
```
-- 条件查询
```
Select * from student1
WHERE sname='东坡';
```

存储引擎

INNODB
MyISAM

创建有主键的表：
```
CREATE table student2(
-- id int(11) PRIMARY KEY ,
id int(11) AUTO_INCREMENT,
sname varchar(100) not NULL,
sage int(3) DEFAULT NULL,
PRIMARY key(`id`)
)ENGINE=InnoDB DEFAULT CHARSET=utf8
```

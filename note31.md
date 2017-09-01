### 对比类选择符与ID选择符的区别：
第一：ID是唯一的,class 是可以重用的,id 在页面浏览器里显示时只能出现一次；CLASS 可以多次，你多个地方都想要同一个样式就这样写。（这里的唯一只是指在一个网页里只能用一次，并不是说在整个网站站点中只能用一次）

第二：在表现形式上 ID 的优先级比 class 高。

第三:方便 JS 等客户端脚本的引用

* a:link{color:#FF0000;textdecoration:underline;}
a:visited { color:#00FF00;text-decoration:none;}  
a:hover { color:#000000;text-decoration:none;}
a:active { color:#FFFFFF;text-decoration:none;}
上述的效果是：定义的链接颜色是红色，访问过后的链接是绿色，鼠标悬浮在链接上时是黑色，点击时的颜色是白色。

子选择器只能用于直接嵌套的父子关系。
```
Div>p{ color:red;}
<div>
  <p>子选择器</p>
</div>
```
子选择器在IE6、IE7、IE8中则是不被支持的选择器

:first-child  元素的第一个子元素添加样式

:last-child  元素的最后一个子元素添加样式

:first-line   匹配第一行样式

:first-letter  元素的第一个字

CSS优先级包含四个级别（文内选择符，ID选择符，Class选择符，元素选择符）以及各级别出现的次数。根据这四个级别出现的次数计算得到CSS的优先”级。
id选择器优先级 > 类class选择器优先级 > 标签选择器优先级

基本选择器 标签、类别、id的优先级：
给同一个元素使用三种基本选择器进行定义
结果：id>class>标签

比较简单易记的一种方法就是给不同选择器分配不同的值：

1.id选择器默认优先级最高，其权值为100

2.class选择器、属性选择器和伪类选择器的权值为10

3.标签选择器的优先级较低，其权值为1
所以在比较样式的优先级时，只需统计选择符中的id、class、标签名个数，然后把对应的权值相加即可。根据结果便可得出优先级高低。

1.结果较大的优先级较高

2.结果相同，则后定义的样式优先级较高

3.如果样式值中含有!important，则该值优先级最高

Css语法 选择器{属性：值；}
css控制页面的三种方式
* 行内样式。
将css样式编码写在XHTML标签中。
* 内部样式。
可单独针对某一页进行设计，将样式信息放在页面一个固定位置上。一般放在head中
* 外部样式表。
```
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css" />
</head>
```
注意：
外部样式表可以在任何文本编辑器中进行编辑。文件不能包含任何的 html 标签。样式表应该以 .css 扩展名进行保存。

color:#fff;  ---字体颜色

   text-decoration:none; ---下划线
   ：无
   display:block; ---显示：块

   background:#093; ---背景

   padding:20px; ---填充距离

   border-top:2px solid #fff;  顶部描边

   list-style:none;无序列表样式

   line-height:  行高  当行高和高度相等时文字会居中

background:url(link.jpg)
  no-repeat 代表不平铺，

  repeat-x  :　 背景图像横向平铺

  repeat-y  :　 背景图像纵向平铺

  #333333： 代表的是颜色值

### 五种长用选择器？

标签选择器(符)

类别选择器(符)

ID选择器(符)

群组选择器(符)

派生选择器(符)也叫包含选择器(符)  

float
  float ---浮动  

  float 它的属性值一共有三个。

  none   left    right

  float：none  不飘浮

  float：left     左边

  float：right    右边

  clear
它表的是清除浮动的意思
  它有四个值
  none  :　 默认值。不清除任何浮动：即允许两边有浮动

  left  :　    清除左侧浮动

  right  :　 清除右侧浮动

  both  :　 清除两边浮动

   background
背景
background:url(link.jpg)

   no-repeat 代表不平铺，

   repeat-x  :　 背景图像横向平铺

   repeat-y  :　 背景图像纵向平铺

   #333333： 代表的是颜色值

   right center left：控制背景位置
   

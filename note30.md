## 什么是选择器？

选择器(selector) 通常是你希望定义的HTML 元素或标签。

例如要改变标题一的大小h1{font-size:12px;},
改变段落文本颜色 p{color:Red}
此时h1、p为选择器。

## 选择器类型

标签选择器
类别选择器
id选择器

CSS 语法由三部分构成：选择器、属性和值：

h2{color:#ff0000; background:#000000;}
其中“h2”,我们称为选择器，指明我们要给“h2”定义样式；
样式声明写在一对大括号“{}”中；
Color和background称为“属性”，不同属性之间用“；”分隔
“#ff0000”和“#000000”是属性的值

### 标签选择器。
就是HTML文档中的元素[作用于html标记]
只针对HTML中标签使用。
语法：p{属性:值}
缺点，由于标签选择器控制的是整个标签所有，控制范围比较大，不灵活

### 类别选择器。
类选择符：可以自己定义样式，应用于一个或多个网页元素，类在网页中可以出现多次，用于定义重复的样式。类以英文“.”开头，后面的名字自己定义，类定义后还需要在网页中加入class=类名称，加以调用。

width      宽

height       高

background ---背景      
float ---浮动   
margin--外边界距离

功能	         语法

设置字号	       font-size:12px

设置字色	       color:#00000

设置字体	       font-family:”黑体”

设置行高	      line-height:150%  
                line-height:1.5em

设置字体的粗细 	      font-weight :
 normal [正常] bold [粗体]

 CSS选择器的构成是：选择器{属性:属性值}
类选择器
标签选择器

### 通配选择符：
* {属性:值}，用于定义所有元素

* 群组选择器(符)
语法：h1,p,ul,li,a,ul li{ font-size:14px;color:#F00;}
相同样式的元素可以进行集体声明。
使用群组选择器，将会大大的简化CSS代码，将具有多个相同属性的元素，合并群组进行选择，定义同样的CSS属性，这大大的提高了编码效率，同时也减少了CSS文件的体积

* 派生选择器(符)如果既想使用id或class，也想同时使用标签选择符
语法：h1 #content{color:#ff0000} 表示针对所有id为content的h1标签
继承与覆盖（反应了层叠的含义）

* id选择符(器)
语法：#名称{属性:属性值}
如：#main{background:#000;font-size:16px;}
如何调用<div id="main"></div>
ID与类别区别：id不能同时在两个标记中使用，有唯一性。而且id不仅仅适用于CSS代码，同样适用在js中，会造成语法混乱。对于页面结构的定义使用id，对于文本等样式的定义多次重复使用的使用class。

* 锚伪类选择器
伪类：是一种特殊的类，由css自动支持，属css的一种扩展类型。伪类的名称不能被用户自定义，必须使用标准格式。

锚，代表超链接。锚伪类是超链接的四种状态。
    未访问状态（a:link）、
鼠标悬停状态（a:hover）、（最常用的属性）

活动状态（a:active）、(在鼠标点击与释放之间发生的事件）

已访问状态（a:visited）

a的四种状态
a:link {color: #FF0000}		/* 未访问的链接 */

a:visited {color: #00FF00}	/* 已访问的链接 */

a:hover {color: #FF00FF}	/* 鼠标移动到链接上 */

a:active {color: #0000FF}	/* 选定的链接 */

* LVHA（爱恨法则 LoVeHAte）
  注意：IE6、FF中必须清空缓存才能查看a:link效果，对缓存依赖性强。
  一般使用锚伪类时只使用 a{ color:red} a:hover{ color:blue}
  例2、通过所学内容完成以下实例：
默认状态为灰色无下划线，鼠标悬停为红色加下划线

伪类与css类、或与id结合使用
  A.red:hover{color:red} /*class=red的a 鼠标悬停状态为红色 A.red强调为指定标签选择器*/
   A#current:hover{color:red}/*用于当前导航效果*/
  <a href="#" id="current">首页</a>
  <a href="#" class="red">新闻</a>

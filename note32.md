### 文档流

是浏览器解析网页的一个重要概念。对于一个xhtml网页，body元素下的任意元素，根据其先后顺序，组成了一个上下关系，这便是文档流。浏览器根据这些元素的顺序去显示它们在网页中的位置。文档流是浏览器的默认显示规则。

简单来说
"文档"就是页面，doctype。。
"流"就指输入输出的形式，其中输入应该是“布局”，输出应该是“显示”
综合起来就是：页面布局和显示的形式。

### 块级元素

在页面中元素一般分为：块级元素（block）、内联(行内)元素（inline）
block元素：独占一行，前面和后面就好像有一个换行符。可以设置宽，高，margin和padding也正常

### 行内元素

inline元素：与其他的内联元素占一行，不可以设置宽高，随自身内容自动变大缩小，不可以设置margin-top,margin-bottom,padding-top,padding-bottom值

* 相互转化
行内元素和块元素之间的可以通过：display：block来进行转换的。
display 它的值有很多，最长用的是三种（其它的值，自己参看css手册）
      display :block  ；(显示隐藏对象)　 把行内元素转为块级元素。
      display :none  ；　 隐藏对象。
      display :inline ； 把块级元素，转换成行内元素。

### span

span标签本身没有什么意义。和div一样，也没
有什么样式。css对其进行控制。
span于div的区别？
     div是块级元素，   span是行内元素
span主要用途？
    <span>可以划分区域把文字归组，用来做一些说明，和特性效果。

块元素（例如div）在没有任何布局属性作用时，默认排列方式是换行排列

内联（行内）元素（例如span、a）在没有任何布局属性作用时，默认排列方式是在同行排列，直到宽度超出包含它的容器宽度时才自动换行。

块级元素，可以设置高度、宽度、内外边距等属性。

行内元素，不可以设置高度、宽度、内外边距等属性。

行内元素和块元素之间的可以通过：display：block来进行转换的。

（1）padding-left:10px; 左内边距

（2）padding-right:10px; 右内边距

（3）padding-top:10px; 上内边距

（4）padding-bottom:10px; 下内边距

（5）padding：10px; 四边统一内边距

（6）padding:10px 20px; 上下、左右内边距

（7）padding:10px 20px 30px; 上、左右、下内边距

（8）padding:10px 20px 30px 40px; 上、右、下、左内边距

可取的值

（1）数值 规定具体单位记的内边距长度
（2）%       基于父元素的宽度的内边距的长度
（3）auto    浏览器计算内边距
（4）inherit 规定应该从父元素继承内边距

指定文字字体 font-size
 Body{font-family: "宋体", "黑体"}
这句代码的意思是，设定的属性值为一个字体组，优先选择使用“宋体”，但是如果用户电脑没有宋体，那么可以选择使用黑体，字体与字体之间使用逗号隔开。

body{color:red}使用关键字设计字体颜色为红色。（不被所有浏览器接受）
body{color:#ffff00}
使用16进制方式设定颜色。（可以被所有浏览器接受。可写成 color：#ff0，代码优化）

xx-small :根据对象字体进行调整。最小       x-small :较小          small:小
medium:正常
large :大       x-large:较大      xx-large :最大
larger :相对父级增大
smaller:相对父级减小

Font-style :normal| italic | oblique
Italic是使用文字的斜体，Oblique是让没有斜体属性的文字倾斜

font-weight : normal | bold | bolder | lighter | 100 | 200 | 300 | 400 | 500 | 600 | 700 | 800 | 900
一般使用bold进行加粗，相当于700
如果去掉默认加粗样式，使用normal

none :　无装饰

blink :　 闪烁(不兼容)

underline :　 下划线

line-through :　 贯穿线

overline :　 上划线

首行文本的缩进 用法
text-indent:1em
允许使用负值。如果使用负值，那么首行会被缩进到左边

text-shadow:#ff0000 1px 1px 3px;
    分别代表：颜色    左右位置   上下位置   模糊值

none  :　 默认值。不转换
capitalize  :　 将每个单词的第一个字母转换成大写，
uppercase  :　 转换成大写
lowercase  :　 转换成小写

font: bold  italic  14px/20px "宋体";  
注意顺序：最后两位必须得是大小和字体，字体在最后
字体粗细   是否倾斜   字体大小/行高  字体样式

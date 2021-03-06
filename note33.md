### 什么是浮动？

浮动（float）是CSS实现布局的一种方式，包括div在内的任何元素都可以以浮动的方式进行显示。

值：

none:不浮动

left:对象向左浮动，而右侧的内容流向对象的右侧

right:对象向右浮动，而左侧的内容流向对象的左侧

浮动的清理(clear)：清理是浮动的另一个有用的工具，实现拒绝浮动对象对后面对象的影响。
技巧：当浮动了许多元素之后，突然需要另起一行时，可以制作一个空白的div标签，为其设置 clear:both;清除左右的浮动。

clear：both
overflow：hidden
定位

div、h1 或 p 元素常常被称为块级元素。这意味着这些元素显示为一块内容，即“块框”。与之相反，span 和 strong 等元素称为“行内元素”，这是因为它们的内容显示在行中，即“行内框”。
我们可以使用display属性来改变元素的框

CSS 有三种基本的定位机制：普通流、浮动和绝对定位。
static 元素框正常生成。块级元素生成一个矩形框，作为文档流的一部分，行内元素则会创建一个或多个行框，置于其父元素中。
 relative 元素框偏移某个距离。元素仍保持其未定位前的形状，它原本所占的空间仍保留。
absolute 元素框从文档流完全删除，并相对于其包含块定位。包含块可能是文档中的另一个元素或者是初始包含块。元素原先在正常文档流中所占的空间会关闭，就好像元素原来不存在一样。元素定位后生成一个块级框，而不论原来它在正常流中生成何种类型的框。
 fixed 元素框的表现类似于将 position 设置为 absolute，不过其包含块是视窗本身。

 鼠标光标的类型（形状）?
cursor
cursor：pointer; 表示鼠标经过是光标变为小手
ID   class 和标签选择器的优先级为？
id>class>标签
css三种调用方式优先级?
行内样式会覆盖其余两种方式，内部样式和外部样式取决于他们在head标签中位置的顺序

### 回顾列表类型？
Ol        定义有序列表

Ul        定义无序列表

Li        定义列表项

Dl        定义定义列表

Dt        定义定义项目

dd        定义定义的描述

list-style-image ----列表样式图片属性

list-style-image:url("heidian.jpg");  有双引号

list-style-position----列表样式位置

后面跟两个属性：outside与inside

outside：代表样式图片显示在文字的外面

inside：代表样式图片显示的文字里面,文字环绕图片,

disc ：实心圆

circle ：空心圆

square ：实心方块

decimal：阿拉伯数字  

lower-roman  ：小写罗马数字

upper-roman ：大写罗马数字  

lower-alpha：小写英文字母

upper-alpha：大写英文字母

list-style: url("img/devgurupix.gif")   inside   circle;

list-style-type:circle
设置列表项标记的类型

list-style-position
设置在何处放置列表项标记(即位置)

此属性有两个值默认的outside
另一个是inside

list-style-image使用图像来替换列表项的标记

css雪碧技术

提高网页显示速度最有效的一个方法是减少页面的HTTP请求次数，为了减少HTTP请求次数，最直接有效的方法是使用精灵图片（CSS sprites），精灵图片是把许多图片放到一张大图片里面，通过CSS来显示图片的一部分。
　网站建设企图时建议使用css精灵整合图片，尤其是比较大的网站，网站上的图片用的比较的网站，因为css精灵的作用就是降低图片文件的http链接请求数，把很多歌图片将以一定间距合并为一个大图片文件。这样页面中应用到的图片元素就可以利用background-position 整个css属性来显示拼合图片中的指定位置

CSS Sprites其实就是把网页中一些背景图片整合到一张图片文件中，再利用CSS的“background-image”，“background-repeat”，“background-position”的组合进行背景定位，background-position可以用数字能精确的定位出背景图片的位置。

利用CSS Sprites能很好地减少了网页的http请求，从而大大的提高了页面的性能，这也是CSS Sprites最大的优点，也是其被广泛传播和应用的主要原因；

诚然CSS Sprites是如此的强大，但是也存在一些不可忽视的缺点

1.在图片合并的时候，你要把多张图片有序的合理的合并成一张图片，还要留好只够的空间，防止板块内不会出现不必要的背景；这些还好，做痛苦的是在宽屏，高分辨率的屏幕下的自适应页面，你的图片如果不够宽，很容易出现背景断裂；

2.CSS Sprites在开发的时候比较麻烦，你要通过photoshop或其他工具测量计算每一个背景单元的精确位置，这是针线活，没什么难度，但是很繁琐；幸好腾讯的鬼哥用RIA开发了一个CSS Sprites 样式生成工具，虽然还有一些使用上的不灵活，但是已经比photoshop测量来的方便多了，而且样式直接生成，复制，拷贝就OK！

3.CSS Sprites在维护的时候比较麻烦，如果页面背景有少许改动，一般就要改这张合并的图片，无序改的地方最好不要动，这样避免改动更多的css，如果在原来的地方放不下，有只能（最好）往下加图片，这样图片的字节就增加了，还要改的css。

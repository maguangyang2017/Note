语法： 

background-position : length || length 

background-position : position || position 

取值： 

length  : 百分数 | 由浮点数字和单位标识符组成的长度值。请参阅 长度单位  

position  : top | center | bottom | left | center | right 

说明： 

设置或检索对象的背景图像位置。必须先指定 background-image 属性。

该属性定位不受对象的补丁属性( padding )设置影响。

默认值为： 0% 0% 。此时背景图片将被定位于对象不包括补丁( padding )的内容区域的左上角。

如果只指定了一个值，该值将用于横坐标。纵坐标将默认为 50% 。如果指定了两个值，第二个值将用于纵坐标。

如果设置值为 right center ，因为 right 作为横坐标值将会覆盖 center 值，所以背景图片将被居右定位。

对应的脚本特性为 backgroundPosition。

### float浮动属性特性

float：none   right    left
1）div加上浮动后，就脱离了文档流，那么表现的就对于它的父级而言就像不存在一样。

2）不论什么元素，加上浮动后都会变成块级元素。
     如：span是行内（内联）元素，设置宽度不起作用，但是加上浮动以后便有了作用。

3）如果不给浮动属性设置宽度，那么它的宽度将会根据它内容的宽度自适应。

### 局限性

浮动定位只能实现左右定位，只能出现在固定的框中。

### 文档流

"文档"就是页面，doctype。
"流"就指输入输出的形式，其中输入应该是“布局”，输出应该是“显示”
综合起来就是：页面布局和显示的形式。

### 公共样式

 body{ font-family:Arial,
    Helvetica, sans-serif,"微软雅黑","宋体"; font-size:12px;                    background:#fff; color:#333;}

  p,h3,h5,body,ul,li,ol,input,img,table{ margin:0; padding:0;}

  ul,li,ol{list-style:none;}

  input,img{border:none;}

   a{ text-decoration:none; color:#333;}

### 定位

属性：position

所有元素在默认状态下是position：static
 定位分为：

静态定位 static 页面中的每一个对象的默认值

绝对定位  absolute  （相对于子元素来说 ，不占空间）

相对定位  relative  （ 相对于父亲元素来说，占有一定空间）  

固定定位  fixed  可以固定在网页的某个地方

好处：可以省去不少请求数量

### 绝对定位

设置为绝对定位的元素框从文档流完全删除，并相对于其包含块定位，包含块可能是文档中的另一个元素或者是初始包含块。元素原先在正常文档流中所占的空间会关闭，就好像该元素原来不存在一样。元素定位后生成一个块级框，而不论原来它在正常流中生成何种类型的框。

position：absolute

绝对定位使元素的位置与文档流无关，因此不占据空间

其位置控制是相对与其父级进行绝对定位的，如果没有这样的父级则相对于body。

可以层叠，叠加，控制其层叠位置的属性是
    z-index ：100；其值可以为负值。

position：absolute
给图层应用绝对定位以margin：0  auto；将对它不起作用。
提示：因为绝对定位的框与文档流无关，所以它们可以覆盖页面上的其它元素。可以通过设置 z-index 属性来控制这些框的堆放次序

### 相对定位

对象不可层叠，并且会占用空间。
属于在正常文档流中偏移位置。
不可层叠。

设置以后margin值也一样起作用。
其位置控制是“相对于”它的原始起点进行移动。

注意，在使用相对定位时，无论是否进行移动，元素仍然占据原来的空间。因此，移动元素会导致它覆盖其它框

### 绝对定位（absolute）与相对定位（relative）的区别？

绝对定位（absolute）不占用空间
可以层叠，控制其层叠的位置的代码是：z-index。

应用绝对定位（absolute）以后，margin值将失效。

其位置控制是相对其父级进行绝对定位的，如果没有这样一个父级的话，则以body为参考定位。

绝对定位（absolute）与相对定位（relative）的相同点？

都是用，left，right，top，bottom来控制移动的位置的。并且都可以为负值。

### 固定定位

position:fixed  为固定位置，可以固定在网页的某个地方，

用，left，right，top，bottom来控制移动的位置的。并且都可以为负值。

负数  负数  ：向左移动   向上移动

正数   正数 ：向右 移动  向下移动

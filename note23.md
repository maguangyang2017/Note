标尺   视图——标尺（ctrl+r）
按住 alt键切换标尺的横竖
隐藏标尺  ctrl+r  
隐藏参考线  ctrl+;或者ctrl+h

什么是选区

1. 选区主要是从来编辑和处理图像。
2.  选区的类型普通选区与羽化选区
普通选区的边缘比较生硬，当在图片上绘图或者拼合图像时候，可以很容易的看到编辑的痕迹。
羽化选区：用来设置选区的边缘的柔化成都，是编辑或者拼合后的图像与原图像浑然一体，天衣无缝。   
   设置羽化的选区在进行移动、剪切、拷贝或者填充选区后，羽化效果很明显。有些选区创建工具提供羽化设置，就可以在创建过程中设置羽化：也可以给已创建好的选区设置羽化。
羽化就是模糊选区的边缘，羽化值越大，边缘就越模糊，这种效果可以很自然的融入其他图层里~
如果没有羽化，你所选择的选区经过处理后，边缘非常明显，而且与其他图层合并的时候非常生硬.

shift   添加到选区
alt   从选区中减去  
shift + alt   与选区交叉

注：

1、 按住shift同时拖动鼠标可创建正方或正圆选区  
2、 在创建选区时，按住alt将创建以鼠标的落点为中心的矩形或椭圆；
3、 按住shift+alt键拖动鼠标可以创建以鼠标的落点为中心的正方形或是圆形选区

4、 创建完选区后，如需移动，将鼠标停放在选区轮廓内，按住鼠标左键并拖动即可。

注：   
单行、单列创建选区，其工具栏属性的“羽化”值为0

羽化的两种方式
1、制作选区前，在属性栏设置属性值（0~250），属性值越大，边缘就越模糊
2、制作选区后，shift+F6设置羽化值

隐藏 标尺（网格）：快捷键 ctrl + H    
 撤销命令键： ctrl+z，只能撤销一次，  ctrl+alt+z：执行很多次
取消选区  ：ctrl +D  选择 -  取消选择
新建文件    ctrl + N   保存  ctrl+s  
 打开文件  ctrl + o    
新建图层    名称  宽高
补充  前景色  Ctrl+ del    背景色  Alt+del
删除图层  del   shift + ctrl + N

（1）套索工具：用于手动地选择出选择区，要求鼠标操作者鼠标运用熟练；
（2）多边形套索工具：用于选择边缘规则的图像，创建主要由直线连成的选区。如果单击鼠标后按住Shift键，则可水平、垂直或者45度角方向绘制直线。
（3）磁性套索工具：用来处理照片，ps自动跟踪边缘，选择具有完整边缘、但不很规则、并与背景反差较大的图像外形。在创建选区时，如果有部分边缘比较模糊，可以按住alt键暂时将工具转换为曲线套索工具或者多边形套索工具继续绘制。

### 移动、复制与删除图像

移动图像是指将当前图层的图像移至同一图像窗口的其他位置图像或其他图像窗口中
移动工具的属性栏（已讲过）
复制图层
按住alt键移动鼠标
注：按住shift可以水平，垂直，45度角移动
删除图层如何删除
注：对齐方式
       键盘上下左右只能一次移动一个像素
       shift+方向键可以一次移动10个像素

图像  》  选择
1.拷贝（ctrl+c）粘贴（ctrl+V）原位粘贴（shift+ctrl+V）
2、合并拷贝 shift+ctrl+C（可以同时复制选区内多个图层中同一位置的内容，并在粘贴时将其合并为一个图层）
3、贴入  shift+alt+ctrl+V

编辑 / 自由变换 ctrl+t
 在编辑---自由变换（Ctrl+T）可以创建变形框，按住Ctrl键拖动控制点可以自由变形，按住Alt键拖动某个控制点可以对称变形，按住Ctrl+Shift键拖动某个控制点可以斜切调整，按住Ctrl+Shift+Alt键可以进行透视调整

   在它的工具属性栏中有一个“在自由变形和自由变换模式下切换”的属性，点击会出现系统自带的形状，如拱形，扇形，鱼眼等；

变换图像是指对图像进行缩放、旋转、扭曲、斜切、透视等操作
注意变换图像是多图像本身进行变形，而变换选区是对选区进行变形，不会影响选区内的图像。
重复变形（ctrl+shift+alt+t）

	撤销一步Ctrl+Z，撤销多步Ctrl+Alt+Z，最多是20步，这和你自己设置的多少步有关系，可以在编辑---首选项--常规，这个地方改他的数值

找历史记录可以查看你当前的状态，利用快照可以迅速的找到你所需要的步骤

### 画笔

可以绘制各类柔和的线条或一些预先定义好的图案
设置笔刷大小快捷键  英文状态下   
属性栏  
   不透明度（值越大，画出来的线条越清晰）
    流量   数值越大，越清晰
【    缩小           】   放大
设置属性快捷键    F5
实例  大树 花  青草，蓝天 白云
载入画笔（如何载入）  编辑  》  定义画笔预设
自定义画笔

可以模拟铅笔的绘画风格，通常用来绘制一些无边缘发散效果的线条或图案
绘制时一般使用的颜色为前景色
按住shift可以绘制一条直线，若按住shift键反复点击并拖动所标，可以自动画出首尾相连的折线

区别: 画笔工具可以绘制比较柔和的线条，铅笔工具可以绘制一些菱角比较突出无边缘发散效果的线条，颜色替换工具可以保留图像纹理和阴影不变的情况下，快速的更改如想任意区域的颜色

仿制图章工具的使用
快捷键  S
利用“仿制图章工具”  可将一幅图像的全部或部分复制到同一幅图像或另一幅图像中。将“仿制图章工具”移至图像窗口中，按住【Alt】键，在图像中单击鼠标左键定义一个参考点。松开【Alt】键，再将鼠标光标移至目标位置，然后单击或拖动，即可将参考点处的图像复制到该位置
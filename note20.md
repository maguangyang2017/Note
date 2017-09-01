### 在Swing中的绘画

Swing起步于AWT基本绘画模式，并且作了进一步的扩展以获得最大化的性能以及改善可扩展性能。象AWT一样，Swing支持回调绘画以及使用repaint()促使部件更新。另外，Swing提供了内置的双缓冲（double-buffering）并且作了改变以支持Swing的其它结构(象边框(border)和UI代理)。最后，Swing为那些想更进一步定制绘画机制的程序提供了RepaintManager API。

### 对双缓冲的支持

Swing的最引人注目的特性之一就是把对双缓冲的支持整个儿的内置到工具包。通过设置javax.swing.JComponent的"doubleBuffered"属性就可以使用双缓冲：
     public boolean isDoubleBuffered()
    public void setDoubleBuffered(boolean o)

当缓冲激活的时候，Swing的双缓冲机制为每个包容层次（通常是每个最高层的窗体）准备一个单独的屏外缓冲。并且，尽管这个属性可以基于部件而设置，对一个特定的容器上设置这个属性，将会影响到这个容器下面的所有轻量级部件把自己的绘画提交给屏外缓冲，而不管它们各自的"双缓冲"属性值

默认地，所有Swing部件的该属性值为true。不过对于JRootPane这种设置确实有些问题，因为这样就使所有位于这个上层Swing部件下面的所有部件都使用了双缓冲。对于大多数的Swing程序，不需要作任何特别的事情就可以使用双缓冲，除非你要决定这个属性是开还是关(并且为了使GUI能够平滑呈现，你需要打开这个属性)。Swing保证会有适宜的Graphics对象(或者是为双缓冲使用的屏外映像的Graphics，或者是正规的Graphics)传递给部件的绘画回调函数，所以，部件需要做的所有事情仅仅就是使用这个Graphics画图。

### 遮光性

在一般情况下部件是不透明的，为了提高改善性能，Swing增加了读写javax.swing.JComponent的遮光(opaque)属性的操作:
    public boolean isOpaque()
    public void setOpaque(boolean o)

这些设置是：
•true：部件同意在它的矩形范围包含的里所有像素位上绘画。
•false：部件不保证其矩形范围内所有像素位上绘画。

遮光(opaque)属性允许Swing的绘图系统去检测是否一个对指定部件的重画请求会导致额外的对其底层祖先的重画。每个标准Swing部件的默认(遮光)opaque属性值由当前的视－感UI对象设定。而对于大多数部件，该值为true。
部件实现中的一个最常见的错误是它们允许遮光(opaque)属性保持其默认值true，却又不完全地呈现它们所辖的区域，其结果就是没有呈现的部分有时会造成屏幕垃圾。当一个部件设计完毕，应该仔细的考虑所控制的遮光(opaque)属性，既要确保透的使用是明智的，因为它会花费更多的绘画时间，又要确保与绘画系统之间的协约履行。
遮光(opaque)属性的意义经常被误解。有时候被用来表示“使部件的背景透明”。然而这不是Swing对遮光的精确解释。一些部件，比如按钮，为了给部件一个非矩形的外形可能会把“遮光”设置为false，或者为了短时间的视觉效果使用一个矩形框围住部件，例如焦点指示框。在这些情况下，部件不遮光，但是其背景的主要部分仍然需要填充。
如先前的定义，遮光属性的本质是一个与负责重画的系统之间订立的契约。如果一个部件使用遮光属性去定义怎样使部件的外观透明，那么该属性的这种使用就应该备有证明文件。(一些部件可能更合适于定义额外的属性控制外观怎样怎样增加透明度。例如，javax.swing.AbstractButton提供ContentAreaFilled属性就是为了达到这个目的。)
另一个毫无价值的问题是遮光属性与Swing部件的边框(border)属性有多少联系。在一个部件上，由Border对象呈现的区域从几何意义上讲仍是部件的一部分。就是说如果部件遮光，它就有责任去填充边框所占用的空间。(然后只需要把边框放到该不透明的部件之上就可以了)。

如果你想使一个部件允许其底层部件能透过它的边框范围而显示出来 -- 即，通过isBorderOpaque()判断border是否支持透明而返回值为false -- 那么部件必须定义自身的遮光属性为false并且确保它不在边框的范围内绘图。

### "最佳的"绘画方案

部件重叠的问题有些棘手。即使没有直接的兄弟部件叠加在该部件之上，也总是可能有非直系继承关系(比如"堂兄妹"或者"姑婶")的部件会与它交叠。这样的情况下，处于一个复杂层次中的每个部件的重画工作都需要一大堆的树遍历来确保'正确地'绘画。为了减少不必要的遍历，Swing为javax.swing.JComponent增加一个只读的isOptimizedDrawingEnabled属性：
    public boolean isOptimizedDrawingEnabled()

这些设置是：

•true：部件指示没有直接的子孙与其重叠。
•false: 部件不保证有没有直接的子孙与之交叠。

通过检查isOptimizedDrawingEnabled属性，Swing在重画时可以快速减少对交叠部件的搜索。
因为isOptimizedDrawingEnabled属性是只读的，于是部件改变默认值的唯一方法是在其子类覆盖(override)这个方法来返回所期望的值。除了JLayeredPane，JDesktopPane，和JViewPort外，所有标准Swing部件对这个属性返回true。

### 绘画方法

适应于AWT的轻量级部件的规则同样也适用于Swing部件 -- 举一个例子，在部件需要呈现的时候就会调用paint() -- 只是Swing更进一步地把paint()的调用分解为3个分立的方法，以下列顺序依次执行：
```
     protected void paintComponent(Graphics g)
    protected void paintBorder(Graphics g)
    protected void paintChildren(Graphics g)
```
Swing程序应该覆盖paintComponent()而不是覆盖paint()。虽然API允许这样做，但通常没有理由去覆盖paintBorder()或者paintComponents()(如果你这么做了，请确认你知道你到底在做什么！)。这个分解使得编程变得更容易，程序可以只覆盖它们需要扩展的一部分绘画。例如，这样就解决先前在AWT中提到的问题，因为调用super.paint()失败而使得所有轻量级子孙都不能显示。

### Swing绘画准则

Swing开发人员在写绘画代码时应该理解下面的准则：
1.对于Swing部件，不管是系统－触发还是程序－触发的请求，总会调用paint()方法；而update()不再被Swing部件调用。
2.程序可以通过repaint()触发一个异步的paint()调用，但是不能直接调用paint()。
3.对于复杂的界面，应该调用带参数的repaint()，这样可以仅仅更新由该参数定义的区域；而不要调用无参数的repaint()，导致整个部件重画。
4.Swing中实现paint()的3个要素是调用3个分离的回调方法： 1.paintComponent()
2.paintBorder()
3.paintChildren()
Swing部件的子类，如果想执行自己的绘画代码，应该把自己的绘画代码放在paintComponent()方法的范围之内。(不要放在paint()里面)。
5.Swing引进了两个属性来最大化的改善绘画的性能： ◦opaque: 部件是否要重画它所占据范围中的所有像素位？
◦optimizedDrawingEnabled: 是否有这个部件的子孙与之交叠？
6.如故Swing部件的(遮光)opaque属性设置为true，那就表示它要负责绘制它所占据的范围内的所有像素位(包括在paintComponent()中清除它自己的背景)，否则会造成屏幕垃圾。
7.把一个部件设置为遮光(opaque)同时又把它的optimizedDrawingEnabled属性设置为false，将导致在每个绘画操作中要执行更多的处理，因此我们推荐的明智的方法是同时使用透明并且交叠部件。  
9.Swing通过JComponent的doubleBuffered属性支持内置的双缓冲，所有的Swing部件该属性默认值是true，然而把Swing容器的遮光设置为true有一个整体的构思，把该容器上的所有轻量级子孙的属性打开，不管它们各自的设定。
10.强烈建议为所有的Swing部件使用双缓冲。
11.界面复杂的部件应该灵活地运用剪切框来，只对那些与剪切框相交的区域进行绘画操作，从而减少工作量。


不管AWT还是Swing都提供了方便的编程手段使得部件内容能够正确地显示到屏幕上。虽然对于大多数的GUI需要我们推荐使用Swing，但是理解AWT的绘画机制也会给我们带来帮助，因为Swing建立在它的基础上。 

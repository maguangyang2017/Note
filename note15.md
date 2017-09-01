### 什么是GUI

图形用户界面（Graphical User Interface，简称 GUI，又称图形用户接口）是指采用图形方式显示的计算机操作用户界面。与早期计算机使用的命令行界面相比，图形界面对于用户来说在视觉上更易于接受。

### Java 基础类 JFC 的基本概念

Java基础类是关于GUI 组件和服务的完整集合，它大大简化了健壮Java 应用程序的开发和实现。 JFC作为JDK1.2的一个有机部分， 主要包含5 个 API： AWT， JavaD， Accessibility，Drag & Drop，Swing。它提供了帮助开发人员设计复杂应用程序的一整套应用程序开发包

正如前面那些模块中所讨论的那样，AWT 组件为Java 应用程序提供了多种 GUI工具。

JavaD 是一图形API，它为Java应用程序提供了一套高级的有关二维（2D）图形图像处理的类。JavaD API 扩展了 java.awt 和 java.awt. image 类，并提供了丰富的绘图风格，定义复杂图形的机制和精心调节绘制过程的方法和类。 这些 API 使得独立于平台的图形应用程序的开发更加简便。

 Accessibility  API提供了一套高级工具，用以辅助开发使用非传统输入和输出的应用程序。它提供了一个辅助的技术接口，如：屏幕阅读器，屏幕放大器，听觉文本阅读器（语音处理）等等

 rag & Drop 技术提供了Java 和本地应用程序之间的互操作性，用来在 Java 应用程序和不支持 Java 技术的应用程序之间交换数据。

  JFC 模块的重点在 Swing。Swing 用来进行基于窗口的应用程序开发，它提供了一套丰富的组件和工作框架，以指定GUI如何独立于平台地展现其视觉效果。

### Swiming是什么

Swing 是 Java 平台的 UI —— 它充当处理用户和计算机之间全部交互的软件。它实际上充
当用户和计算机内部之间的中间人。

Swing组件是Java语言提供的第二代GUI设计工具包它以AWT为基础在AWT内容的基础上新增或改进了一些GUI组件使得GUI程序功能更强大设计更容易、更方便。"Swing"是开发新组件的项目代码名现在这个名字常用来引用新组件和相关的API.

https://github.com/maguangyang2017/Note/blob/master/photo/360截图20170901195056415.jpg

https://github.com/maguangyang2017/Note/blob/master/photo/360截图20170901195144863.jpg

### 什么是AWT

AWT 是抽象窗口工具集（Abstract Window Toolkit）的英文缩写。为用户界面程序提供所需要的组件，例如按钮、标签、复选框、下拉菜单、画布、文本输入区、列表等。此外，AWT还提供事件类、监听器类、图形处理工具、2D 图形等的支持。AWT 存在缺少剪贴板、打印支持等缺陷，甚至没有弹出式菜单和滚动窗口等。

Swing：不是真正使用原生平台提供设备，而是仅仅在模仿，因此可以在任何平台上使用Swing 图形用户界面组件。Swing 绝大部分组件都是轻量级组件，它不像重量级组件那样必须在它们自己本地窗口中绘制，而是在它们所在的重量级窗口中绘制。它比AWT适应性更强。

https://github.com/maguangyang2017/Note/blob/master/photo/360截图20170901195806584.jpg

### Swing程序

https://github.com/maguangyang2017/Note/blob/master/photo/360截图20170901195816388.jpg

### 什么是组件

组件构成图形界面零部件面板按钮下拉选等等,具有图形界面，并能完成一定功能的封装体。

### 什么是容器

用于包含其它组件的组件。

### 组件JComponent

Swing 的整个可视组件库的基础构造块是 JComponent。它是所有组件的父类。它是一个抽象类，所以不能创建 JComponent对象，但是作为类层次结构的结果，从字面意义来说它包含了数百个函数，Swing 中的每个组件都可以使用这些函数。

1.JComponent 不仅是 Swing 组件的基类，还是定制组件的基类

2.它为所有组件提供了绘制的基础架构 —— 一 些方便进行组件定制的东西

3.它知道如何 处理所有的键盘按键。所以类只需要侦听特定的键。

4.它包含 add() 方法，可以添加其他 JComponent。换种方式来看，可以把任意 Swing 组件添加到其他任何 Swing 组件，从而构造嵌套组件（例如，JPanel 包含 JButton，甚至包含一些古怪的组合，例如 JMenu 包含 JButton）。

### Swing组件

https://github.com/maguangyang2017/Note/blob/master/photo/360截图20170901195144863.jpg

JApplet Java.applet.Applet类的扩展，它含有JRootPane的一个实例

JButton 能显示文本和图形的按钮，它是AWT按钮组件的替代组件

　　JCheckBox 能显示文本和图形的复选框，它是AWT选择组件的替代组件

　　JCheckBoxMenuItem 一个复选框菜单项，它是AWT的复选框菜单项组件的替代组件

　　JComboBox 带下拉列表的文本框，它是AWT选择组件的替代组件

　　JComponent 所有轻量J组件的基类

　　JDesktopPane 内部窗体的容器

　　JDialog　Swing对话框的基类，它扩展了AWT Dialot类

　　JEditorPane 用于编辑文本的文本窗格

　　JFrame 扩展java.awt.Frame的外部窗体

　　JInternalFrame 在JDesktopPane中出现的内部窗体

　　JLabel 可显示文本和图标的标签，它是AWT标签组件的替代组件

　　JLayeredPane 能够在不同层上显示组件的容器

　　JList 显示选项列表的组件，它是AWT列表组件的替代组件

　　JMenu 菜单条中显示的一个菜单，它是AWT菜单组件的替代组件

　　JMenuBar 用于显示菜单的菜单条，它是AWT菜单条组件的替代组件

　　JMenuItem 菜单项，它是AWT菜单项组件的替代组件

　　JOptionPane 显示标准的对话框，如：消息和问题对话框

　　JPanel 通用容器，它是AWT面板和画布组件的替代组件

　　JPasswordfield JTextField的扩展，使输入的字符不可见

　　JPopupMenu 弹出式菜单，它是AWT弹出式菜单组件的替代组件

　　JProgressBar 进度指示器

　　JRadioButton 单选按钮，它是AWT复选框组件的替代组件

　　JRootPane 顶层容器，它包含一个玻璃窗格，一个层窗格，一个内容窗格和一个可选的菜单条

　　JScrollBar 滚动条，它是AWT滚动条组件的替代组件

　　JScrollPane 滚动窗格，它是AWT滚动窗格组件的替代组件

　　JSeparator 水平或垂直分隔条

　　JSlider 滑杆

　　JSplitPane 有两个分隔区的容器，这两个分隔区可以水平排列或者垂直排列且分隔区的大小能自动调整

　　JTabbedPane 带选项卡的窗格

　　JTable 表格

　　JTableHeader 表格头

　　JTextArea 用于输入多行文本的文本域，它是AWT文本域组件的替代组件

　　JTestComponent 文本组件的基类，它替代AWT的TextComponent类

　　JTextField 单行文本域，它替代AWT的单行文本域组件

　　JTextPane 简单的文本编辑器

　　JToggleButton 两种状态的按钮，它是JCheckBox和JRadioButton组件的基类

　　JToolBar 工具条

　　JToolTip 当光标停留在一个组件上时，该组件上显示的一行文字

　　JTree 用于按钮层次组织数据的结构控件

　　JViesport 用于浏览可滚动组件的视口

　　JWindow 外部窗口，它是java.awt.Window的扩展

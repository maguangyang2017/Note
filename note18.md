## 事件的产生

鼠标事件的事件源往往与容器相关，当鼠标进入容器、离开容器，或者在容器中单击鼠标、拖动鼠标时都会发生鼠标事件。java语言为处理鼠标事件提供两个接口：MouseListener，MouseMotionListener接口。

### 事件类

(1) getX()：鼠标的X坐标
    (2) getY()：鼠标的Y坐标
    (3) getModifiers()：获取鼠标的左键或右键。
    (4) getClickCount()：鼠标被点击的次数。
    (5) getSource()：获取发生鼠标的事件源。

事件源注册监听器的方法是：
addMouseListener(监视器)：加放监视器。
removeMouseListener(监视器)：移去监视器

### MouseListener/监听器

要实现的MouseListener接口的方法有：
 (1) mousePressed(MouseEvent e);// 鼠标按键在组件上按下时调用。
 (2) mouseReleased(MouseEvent e);//鼠标按钮在组件上释放时调用。
 (3) mouseEntered(MouseEvent e);//鼠标进入到组件上时调用。
 (4) mouseExited(MouseEvent e);//鼠标离开组件时调用。
 (5) mouseClicked(MouseEvent e);//鼠标按键在组件上单击（按下并释放）时调用。
如果程序希望进一步知道按下或点击的是鼠标左键或右键，鼠标的左键或右键可用InputEvent类中的常量BUTTON1_MASK和BUTTON3_MASK来判定。例如，以下表达式判断是否按下或点击了鼠标右键：
    e.getModifiers()==InputEvent. BUTTON3_MASK

### MouseMotionListener接口

MouseMotionListener接口处理拖动鼠标和鼠标移动两种事件。

 注册监视器的方法是：
    addMouseMotionListener(监视器)
要实现的的接口方法有两个：
(1) mouseDragged(MouseEvent e)
(2) mouseMoved(MouseEvent e)

鼠标指针形状也能由程序控制 ，setCursor()方法能设置鼠标指针形状。例如，代码setCursor(Cursor.getPredefinedCursor(cursor.WAIT_CURSOR))。

### 键盘

在Java中与键盘事件有关的接口和类主要有KeyListener、KeyAdapter及KeyEvent。其中KeyListener和KeyAdapter用于监听键盘事件的发生并将其传送到相应的事件处理方法中去，而KeyEvent主要用于提供事件发生时的有关信息。
KeyListener接口能够监听的键盘事件有3种：键按下（Pressed）、键释放（Released）及键的按下并释放（Typed），相应的事件处理方法如下。
（1）public void keyTyped(KeyEvent e)  当键盘上的一个键被按下并释放后该方法被调用。
（2）public void keyPressed(KeyEvent e)  当键盘上的一个键盘被按下后该方法被调用。
（3）public void keyReleased(KeyEvent e)  当键盘上的一个键盘被释放时该方法被调用。

### KeyEvent类中常用的方法如下

（1）public int getKeyCode()  返回键盘事件中相关键的整数类型键码。
（2）public char getKeyChar()  返回键盘事件中相关键的字符类型键码。例如，对于Shift+a键返回的字符是A。
（3）public static String getKeyText(int keyCode)  返回一个描述由参数int keyCode指定的键的字符串，如"HOME"，"F1" 或"A".等。
（4）public String paramString()  返回一个标识该事件的参数字符串。




下面是某些特殊键的虚拟键码。 键码 含义 键码 含义 VK_LEFT/VK_RIGHT 左右方向键
VK_CONTROL Ctrl键 VK_KP_UP 小键盘向上 VK_ATL Alt键 VK_PAUSE 暂停键 VK_SHIFT Shift键 VK_NUMBER0 小键盘数字0 VK_F1 功能键F1 VK_0 数字键0 VK_B 字母键B  

虚拟键码对应的是键位，不区分大小写。要想知道大小写还必须查看修饰键(modifier key)。这由输入事件InputEvent的getModifere()方法得到，把返回值与常量SHIFT_MASK, CONTROL_MASK, ALT_MASK比较，用以判定哪个修饰键处于“同时按下”状态。 

## JLabel

Swing 库中最基础的组件是 JLabel。

不太吸引人，但是仍然有用。实际上，在整个应用程序中，不仅把 JLabel 用作文本描述，还将它用作图片描 述。每当在 Swing 应用程序中看到图片的时候，它就有可能是 JLabel。基本的方法包括设置文本、图片、对齐以及标签描述的其他组件：

get/setText(): 获取/设置标签的文本。
get/seticon(): 获取/设置标签的图片。
get/setHorizontalAlignment(): 获取/设置文本的水平位置。
get/setVerticalAlignment(): 获取/设置文本的垂直位置。
get/setDisplayedMnemonic(): 获取/设置标签的访问键（下划线文字）。
get/setLableFor(): 获取/设置这个标签附着的组件，所以当用户按下 Alt+访问键时，焦点转移到指定的组件。

## JButton

Swing 中的基本动作组件 JButton，是与每个窗口中都能看到的 确定（OK） 和 退出（Cancel） 一样的按钮；这些按钮所做的正是你 希望它们做的工作 —— 在单击它们之后，将发生一些事情。到底会发生什么呢？必须定义发生的内容（这个就是事件处理）。

用来改变 JButton 属性的方法与 JLabel 的方法类似（在大多 数 Swing 组件中，这些属性都类似）。它们控制文本、图片和方向：

get/setText(): 获取/设置标签的文本。
get/seticon(): 获取/设置标签的图片。
get/setHorizontalAlignment(): 获取/设置文本的水平位置。
get/setVerticalAlignment(): 获取/设置文本的垂直位置。
get/setDisplayedMnemonic(): 获取/设置访问键（下划线字符），与 Alt 按钮组合时，造成按钮单击。

除了这些方法，我还学习 JButton 包含的另外一组方法。这些方法利用 了按钮的所有不同状态。状态是对组件进行描述的一个属性，通常采用真/假设置。在 JButton 中，可以包含以下可能状态：活动/不活动、选中/没选中、鼠标经过/鼠标离开、按下/没按下，等等。另外，可以组合这些状态，例如按钮可以在鼠标经过的同时被选中。那么这些如何完成。作为示例，请看看你的浏览器上的后退按钮。请注意在鼠标经过它的时候，图片是如何变化的，在按下该按钮时，图片又是如何变化的。这个按钮利用了不 同的状态。每个状态采用不同的图片，这是提示用户交互正在进行的一种普遍并且有效的方式。JButton 上的状态方法是：

get/setDisabledIcon()
get/setDisableSelectedIcon()
get/setIcon()
get/setPressedIcon()
get/setRolloverIcon()
get/setRolloverSelectedIcon()
get/setSelectedIcon()

## JTextField

Swing 中的基本文本组件是 JTextField，它允许用户在 UI 中输入文本。你们所熟悉文本字段：要掌握本他，则必须使用一个文本字段输入用户名和口令。输入文本、删除文本、选中文本、把 文字四处移动 —— Swing 替你负责所有这些工作。作为 UI 开发人员，利用 JJTextField 时，实际上并不需要做什么。

在处理 JTextField 时，只需要关注一个方法 —— 这应当是很明显的，这个方法就是设 置文本的方法： get/setText()，用于获取/设置 JTextField 中的文本。

## JFrame

迄今为止，我介绍了 Swing 的三个基本构造块：标签、按钮和文本字段；但是现在需要个地方放它们，希望用户知道如何处理它们。JFrame 类就是做这个的——它是一个容器，允许你把其他组件添加到它里面，把它们组织起来，并把它们呈现给用户。它有许多其他好处：

JFrame 实际上不仅仅让你把组件放入其中并呈现给用户。比起它表面上的简单性，它实际上是 Swing 包中最复杂的组件。为了最大程度地简化组件，在独立于操作系统的 Swing 组件与实际运行这些组件的操作系统之间，JFrame 起着桥梁的作用。JFrame 在本机操作系统中是以窗口的形式注册的，这么做之后，就可以得到许多熟悉的操作系统窗口的特性：最小化/最大化、改变大小、移动。但是对于目前来说，把 JFrame 当作放置组件的调色板就足够了。可以在 JFrame 上调用的一些修改属性的方法是：

get/setTitle(): 获取/设置帧的标题。
get/setState(): 获取/设置帧的最小化、最大化等状态。
is/setVisible(): 获取/设置帧的可视状态，换句话说，是否在屏幕上显示。
get/setLocation(): 获取/设置帧在屏幕上应当出现的位置。
get/setsize(): 获取/设置帧的大小。
add(): 将组件添加到帧中。

## JComboBox

JComboBox 的重要函数包括 JComboBox 包含的数据。需要有一种方法来设置 JComboBox 中的数据、修改数据、在用户选择时得到用户的选择。可以使用以下 JComboBox 方法：

addItem()：添加一个项目到 JComboBox.
get/setSelectedIndex()：获取/设置 JComboBox 中选中项目的索引。
get/setSelectedItem()：获取/设置选中的对象。
removeAllItems()：从 JComboBox 删除所有对象。
remoteItem()：从 JComboBox 删除特定对象。

## JTextField

JTextField 的一个细微变化是 JPasswordField，它允许您隐藏在文本字段区域中显示的字符。

get/setEchoChar()：获取/设置每次字符输入时在 JPasswordField 中显示的字符。在获取口令时，不会返回“回声”，而是返回实际的字符。

getText()： 不应当 使用这个函数，因为它会带来可能的安全问题（String 会保存在内存中，可能的堆栈转储会暴露口令）。

getPassword()：这是从 JPasswordField 中获得口令的恰当方法，因为它返回一个包含口令的 char[]。为了保证恰当的安全性，数组应当被清为 0，以确保它不会保留在内存中。


## JCheckBox/JRadioButton

JCheckBox 和 JRadioButton 组件向用户呈现选项，通常采用多选的格式。区别是什么？从实践的角度来说，它们没有那么不同。它们的行为方式相同。但是，在一般的 UI 实践中，它们有细微差异：JRadioButton 通常组合在一起，向用户呈现带有必选答案的问题，而且这些答案具有强制性（这意味着问题只能有一个答案）。JRadioButton 的行为保证了这个用法。一旦选择了JRadioButton，就不能取消对它的选择，除非选择了在同一组中的另外一个单选钮。从效果上看，这就保证了选项的惟一和必选。JCheckBox 的不同在于，允许随机地选择/取消除选择，并允许为问题选择多个答案。

这里是个示例。问题“您是男孩还是女孩!”有两个惟一答案选项“男孩”或“女孩”。用户必须选择一个，不能同时选中。另一方面，问题“您的习惯是什么？”的答案有“跑步”、“睡觉”或“阅读”，不应当只允许为此问题选择一个答案，因为人们可能有不止一个习惯。

它允许把选项组织在一起（例如“男孩”和“女孩”），把这些 JCheckBox 或 JRadioButton 捆绑成一组的类是 ButtonGroupde 类这样，其中一个被选择时，另外一个就自动取消选择。

需要记住的重要的 ButtonGroup 方法是：

add()：添加 JCheckBox 或 JRadioButton 到 ButtonGroup。
getElements()：获得 ButtonGroup 中的全部组件，允许对它们进行迭代，找到其中选中的那个。

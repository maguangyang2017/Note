## JMenu/JMenuItem/JMenuBar(菜单、菜单项、菜单条)

JMenu、JMenuItem 和 JMenuBar 组件是在 JFrame 中开发菜单系统的主要构造块。任何菜单系统的基础都是 JMenuBar。它平淡而乏味，但却是必需的，因为每个 JMenu 和 JMenuItem 都要用它构建。要用 setJMenuBar() 方法把 JMenuBar 附着到 JFrame。一旦将它附加到 JFrame 中，就可以添加所有想要的菜单、子菜单和菜单项。

 JMenu/JMenuItem 的区别看起来可能很明显，但实际上，在幕后看起来并不像表面那样。看看类的类层次结构，就知道JMenude 是 JMenuItemde的子类。但是，在表面上，它们是有区别的：用 JMenu 包含其他 JMenuItem 和 JMenu；JMenuItem 在选中时触发操作。

 JMenuItem 也支持快捷键的概念。与您用过的大多数应用程序一样，Swing 应用程序允许您按下 Ctrl+（某个键）来触发一个操作，就像选中菜单键本身一样。想想用来剪切和粘贴的快捷键 Ctrl+X 和 Ctrl+V。

  除此之外，JMenu 和 JMenuItem 都支持访问键。用 Alt 键与某个字母关联，模拟菜单本身的选择（例如，在 Windows 中按下 Alt+F，然后按下 Alt+x 就可以关闭应用程序）。

### 菜单条

类JMenuBar的实例就是菜单条。例如，以下代码创建菜单条对象menubar：

JMenuBar menubar = new JMenuBar();
在窗口中增设菜单条，必须使用JFrame类中的setJMenuBar()方法。例如，代码：setJMenuBar(menubar);

类JMenuBar的常用方法有：
1.add(JMenu m)：将菜单m加入到菜单条中。
2. countJMenus()：获得菜单条中菜单条数。
3. getJMenu(int p)：取得菜单条中的菜单。
4. remove(JMenu m)：删除菜单条中的菜单m。

### 菜单

由类JMenu创建的对象就是菜单。类JMenu的常用方法如下：
1. JMenu()：建立一个空标题的菜单。
2. JMenu(String s)：建立一个标题为s的菜单。
3. add(JMenuItem item)：向菜单增加由参数item指定的菜单选项。
4. add(JMenu menu)：向菜单增加由参数menu指定的菜单。实现在菜单嵌入子菜单。
5. addSeparator()：在菜单选项之间画一条分隔线。
6. getItem(int n)：得到指定索引处的菜单项。
7. getItemCount()：得到菜单项数目。
8. insert(JMenuItem item,int n)：在菜单的位置n插入菜单项item.
9. remove(int n)：删除菜单位置n的菜单项
10. removeAll()：删除菜单的所有菜单项。

### 菜单项

类JMenuItem 的实例就是菜单项。类JMenuItem的常用方法如下：
1. JMenuItem()：构造无标题的菜单项。
2. JMenuItem(String s)：构造有标题的菜单项。
3. setEnabled(boolean b)：设置当前单项是否可被选择。
4. isEnabled()：返回当前菜单项是否可被用户选择。
5. getLabel()：得到菜单项的名称。
6. setLabel()：设置菜单选项的名称。
7. addActionListener(ActionListener e)：为菜单项设置监视器。监视器接受点击某个菜单的动作事件。

### 设置菜单项的快捷键

用MenuShortcut类为菜单项设置快捷键。构造方法是MenuShortcut(int key)。其中key可以取值KeyEvent.VK_A至KenEvent.VK_Z,也可以取 ‘a’到 ‘z’键码值。菜单项使用setShortcut(MenuShortcut k)方法来设置快捷键。

setAccelerator(KeyStroke.getKeyStroke('N',InputEvent.CTRL_MASK));

### JList

列表(JList)在界面中表现为列表框，是JList类或它的子类的对象。程序可以在列表框中加入多个文本选择项条目。
JList 类的常用构造方法： 1. JList()：建立一个列表。
2. JList(String list[])：建立列表，list是字符串数组，数组元素是列表的选择条目。

JList类的常用方法： 1. getSelectedIndex()：获取选项的索引。返回最小的选择单元索引；只选择了列表中单个项时，返回该选择。
2. getSelectedValue()：获取选项的值。
3. getSelectedIndices()：返回所选的全部索引的数组（按升序排列）。
4. getSelectedValues(),：返回所有选择值的数组，根据其列表中的索引顺序按升序排序。
5. getItemCount()：获取列表中的条数。
6. setVisibleRowCount(int n)：设置列表可见行数。
7. setSelectionMode(int seleMode)：设置列表选择模型。选择模型有单选和多选两种。 • 单选：ListSelectionModel.SINGLE_SELECTION.
• 多选：ListSelectionModel.MULTIPLE.INTERVAL_SELECTION.

8. remove(int n)：从列表的选项菜单中删除指定索引的选项。
9. removeAll()：删除列表中的全部选项。

 列表可以添加滚动条，列表添加滚动条的方法是先创建列表，然后再创建一个JScrollPane滚动面板对象，在创建滚动面板对象时指定列表。以下代码示意为列表list2添加滚动条：
    JScrollPane jsp = new JScrollPane(list2);

## 布局管理

在界面设计中，一个容器要放置许多组件，为了美观，为组件安排在容器中的位置，这就是布局设计。java.awt中定义了多种布局类，每种布局类对应一种布局的策略。只要调用 setLayout(yourLayout） 设置布局管理器即可常用的有以下布局类：
1．• FlowLayout,依次放置组件。
2．• BoarderLayout,将组件放置在边界上。
3．• CardLayout,将组件像扑克牌一样叠放，而每次只能显示其中一个组件。
4．• GridLayout,将显示区域按行、列划分成一个个相等的格子，组件依次放入这些格子中。
5．• GridBagLayout,将显示区域划分成许多矩形小单元，每个组件可占用一个或多个小单元。
    其中GridBagLayout能进行精细的位置控制，也最复杂。暂不将作为重点。
    每个容器都有一个布局管理器，由它来决定如何安排放入容器内的的组件。布局管理器是实现LayoutManager接口的类。

## FlowLayout布局 (JApplet,JPanel,JScrollPane默认布局)

FlowLayout布局是将其中的组件按照加入的先后顺序从左到右排列，一行满之后就转到一下行继续从左到右排列，每一行中的组件都居中排列。这是一种最简便的布局策略，一般用于组件不多的情况，当组件较多时，容器中的组件就会显得高低不平，各行长短不一。

FlowLayout是小应用程序和面板默认布局，FlowLayout布局的构造方法有：
1. FlowLayout(),生成一个默认的FlowLayout布局。默认情况下，组件居中，间隙为5个像素。
2. FlowLayout(int aligment),设定每行的组件的对齐方式。alignment取值可以为 FlowLayout.LEFT,FlowLayout.CENTER,FlowLayout.RIGHT。
3. FlowLayout(int aligment,int horz, int vert),设定对齐方式，并设定组件的水平间距horz和垂直间距vert，用超类Container的方法setLayout()为容器设定布局。例如，代码setLayout(new FlowLayout())为容器设定 FlowLayout布局。将组件加入容器的方法是add(组件名)。

## BorderLayout布局(JWindow、JFrame,JDialog的默认布局)

BorderLayout布局策略是把容器内的空间简单划分为东“East”,西 “West”,南 “South”,北 “North”，中 “Center”五个区域。加入组件时，都应该指明把组件放在哪一个区域中。一个位置放一个组件。如果某个位置要加入多个组件，应先将要加入该位置的组件放放另一个容器中，然后再将这个容器加入到这个个位置。

BorderLayout布局的构造方法有：
(1) BorderLayout(),生成一个默认的BorderLayout布局。默认情况下，没有间隙。
(2) BorderLayout(int horz,int vert),设定组件之间的水平间距和垂直间距。

BorderLayout布局策略的设定方法是setLayout(new BorderLayout())。将组件加入到容器的方法是add(组件名，位置)，如果加入组件时没有指定位置，则默认为“中”位置。

BorderLayout布局是JWindow、JFrame,JDialog的默认布局。

## GridLayout布局

GridLayout布局是把容器划分成若干行和列的网格状，行数和列数由程序控制，组件放在网格的小格子中。GridLayout布局的特点是组件定位比较精确。由于GridLayout布局中每个网格具有相同形状和大小，要求放入容器的组件也应保持相同的大小。

GridLayout布局的构造方法有：
(1) GridLayout(),生成一个单列的GridLayout布局。默认情况下，无间隙。
(2) GridLayout(int row,int col),设定一个有行row和列col的GridLayout布局。
(3) GridLayout(int row,int col,int horz,int vert),设定布局的行数和列数、组件的水平间距和垂直间距。

GridLayout布局以行为基准，当放置的组件个数超额时，自动增加列；反之，组件太少也会自动减少列，行数不变，组件按行优先顺序排列(根据组件自动增减列)。GridLayout布局的每个网格必须填入组件，如果希望某个网格为空白，可以用一个空白标签(add(new Label()))顶替。

GridLayout布局要求所有组件的大小保持一致，这可能会使用界面外观不够美观。一个补救的办法是让一些小组件合并放在一个容器中，然后把这个容器作为组件，再放入到GridLayout布局中。这就是前面所说的容器嵌套。例如，容器A使用GridLayout布局，将容器均分为网格；另有容器B和C各放入若干组件后，把B和C分别作为组件添加到容器A中。容器B和C也可以设置为GridLayout布局，把自己分为若干网格，也可以设置成其他布局。这样，从外观来看，各组件的大小就有了差异。

## CardLayout布局

采用CardLayout布局的容器虽可容纳多个组件，但是多个组件拥有同一个显示空间，某一时刻只能显示一个组件。就像一叠扑克牌每次只能显示最上面的一张一样，这个显示的组件将占据容器的全部空间。CardLayout布局设计步骤如下：
 先创建CardLayout布局对象。然后，使用setLayout()方法为容器设置布局。最后，调用容器的add()方法将组件加入容器。CardLayout布局策略加入组件的方法是：
    add(组件代号，组件);
其中组件代号是字符串，是另给的，与组件名无关。

 例如，以下代码为一个JPanel容器设定CardLayout布局：
    CardLayout myCard = new CardLayout();//创建CardLayout布局对象
    JPanel p = new JPanel();//创建Panel对象
    p.setLayout(myCard);

用CardLayout类提供的方法显示某一组件的方式有两种：
(1) 使用show(容器名，组件代号)形式的代码，指定某个容器中的某个组件显示。例如，以下代码指定容器p的组件代号k，显示这个组件：
    myCard.show(p,k);
 (2) 按组件加入容器的顺序显示组件。
first(容器)：例如，代码myCard.first(p);
 last(容器)：例如 ， myCard.last(p);
 next(容器)：例如，myCard.next(p);
 previous(容器):myCard.previous(p);

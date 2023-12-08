#                                      Unity学习

# 一、下载、安装、操作

1.下载及安装一路平推未遇到问题

* 需要创建分支，在修改好后合并到master中
* 创建分支后无法推送至远程仓库
* fatal: unable to access 'https://github.com/Eve-15/Unity.git/': Failed to connect to github.com port 443 after 21073 ms: Couldn't connect to server

2.在创建项目时出现问题

* vscode上创建一个新项目后却无法推送至远程仓库
* fatal: unable to access 'https://github.com/Eve-15/Unity.git/': Recv failure: Connection was reset

# 二、Unity Hub

### 1.基础

1. 安装
2. 创建项目Ruby's Adventure
3. 导入资源

### 2.主要面板

#### 1.项目面板（project window）

项目面板显示当前项目中的所有文件和目录，包含了所有我们在这个项目里的资源文件，包括：图片，声音，模型，脚本等

#### 2.输出面板（Console window）（不属于五大面板）

输出面板会显示当前游戏开发中生成的警告错误，一些会为我们提供如何去修复这些错误的输出信息，参考这些信息会帮助我们修复这些错误

#### 3.层次面板（Hierarchy window）

层次面板会显示当前**场景**中的所有**游戏物体**对象，并显示**父子级关系**

* 游戏是由一个个场景组成

* 场景中的所有东西都可以称为游戏物体
* 父与子关系及隶属关系

#### 4.场景演示面板（Scene view)

场景面板是当前加载的场景和层次视图中所有游戏对象的实时预览窗口

#### 5.游戏演示面板（Game View）

游戏面板是测试游戏时将显示内容的窗口面板，也是最后我们做出游戏给玩家们玩的时候，他们所看到的画面

#### 6.检视面板（Inspector Window）

当我们在工程面板或者层次面板中选中一个对象时，检视面板会显示它所有的数据，并且我们可以修改

### 3.组件的概念与理解

游戏对象由一个个组件组成

* 双击组件会聚焦（或者F键）
* ctrl+z撤回或者回滚
* ctrl+y上一步

#### 1.Transform组件（最重要）：

三个属性

1. position(位置)
2. rotation(旋转)
3. scale(缩放)

#### 2.Sprite Renderer组件（精灵渲染器）：

负责图像渲染没有的话就看不到图像

### 4.工具栏中的运行按钮

#### 1.Play（运行按钮）

运行按钮用于测试当前在层次面板中放置的游戏物体加载后的游戏运行情况

#### 2.Pause（暂停按钮）

暂停在游戏面板里的游戏测试，帮助发现游戏问题

#### 3.Step（逐帧运行按钮）

逐帧运行按钮用于逐帧遍历暂停的游戏场景

### 5.操作对象的工具按钮

#### 1.Hand Tool（视野查看工具）

可以拖拽移动当前视野，快捷键Q。选中此工具时，按下左键，鼠标滚轮（中间）或Alt+左键可以拖拽移动视野。按下Alt+右键或滚动鼠标滚轮可以放大或者缩小视野

#### 2.Move Tool（移动工具）

可以将选中的物体进行移动，快捷键W

#### 3.Rotate Tool（旋转工具）

可以将选中的物体进行旋转，快捷键E。

#### 4.Scale Tool（缩放工具）

可以将选中的物体进行大小缩放，快捷键R

#### 5.Rect Transform Tool（矩形工具）

可以查看和编辑2D游戏物体的rectTransform组件，可以移动缩放旋转2D和UI等等游戏物体，快捷键T。按下shift键可以等比缩放游戏对象

#### 6.Move，Rotate or scale selected objects（多功能工具）

快捷键y，可以一次进行多种功能，移动，缩放，旋转。

# 三、角色Ruby的创建

### 1.游戏物体的坐标与坐标系

ps：父对象下的子对象在坐标改变时是相当对于父对象移动的（或者插值的）

### 2.类（组件）

```c#
public calss RuByController : MonoBehaviour
{
   void Start()
   {

   }//函数，方法（功能）

   void Update()
   {

   }//函数，方法（功能）
}
```

### 3.函数：

#### 1.Start():

当游戏开始时，Unity只在Start中执行一次代码，且在第一帧更新之前调用

**Start函数是最后调用的**

#### 2.Update():

编写希望游戏中连续发生的事件ps：每秒调用60次

#### 3.函数赋值顺序：

##### 1.变量在声明出来时直接给初值是最先发生

##### 2.在Inspector面板中设置的值

##### 3.在Start函数里进行的赋值

### 4.变量（Variable）：

 是我们在计算机内存中命名的位置（这个由自己命名的），可以使用这个变量获取到在那里存储的值。

### 5.变量类型：

告诉计算机要存储那种数据，以便可以在内存中获得适当的空间量

#### 1.Vector2变量类型：

一种存储两个数字的数据类型，存储在Inspector面板里关于transform组件中positon的x，y值

#### 2.float变量类型：

用于存储小数的变量类型

#### 3.int变量类型：

用来存取整数的变量类型。

### 6.Unity输入系统

#### 1.组成

1.input settings(输入设置)

监听玩家按下键盘的某些键来控制游戏角色的移动

2.输入代码

#### 2.Unity中的输入设置

##### 1.轴向输入

```c#
float horizontal = Input.GetAxis("Horizontal"); 
Debug.Log(horizontal);
```

#### 3.Unity控制面板中的信息输出方法

带括号的是一种方法

```c#
Input.GetAxis("Horizontal")//Input是类,GetAxis是方法，("Horizontal")是参数。
```

# 四、角色RuBy的移动

快捷键

ctrl+k+c全部注释

ctrl+k+u解除全部注释

```c#
void Update()
    {
        float horizontal = Input.GetAxis("Horizontal");
        float vertical = Input.GetAxis("Vertical");
        Vector2 position = transform.position;
        position.x = position.x + 0.1f*horizontal;
        position.y = position.y + 0.1f*vertical;

        transform.position = position;
    }
```

水平方向：Horizontal

垂直方向：Vertical

### 1.调整移动速度

 ```c#
 position.x = position.x + 0.1f*horizontal*horizontal*Time.deltaTime;
 ```

*Time.deltaTime以每秒0.1米的速度移动



```c#
Application.targetFrameRate = 10;
```

将帧率改为10

# 五、2D关卡场景的传统制作方法

多选的快捷键shift选中第一个对象不松手再选中最后一个对象

### 1.Tilemap

在Hierarchy菜单中右键在2D Object中选择Tilemap

#### 网格（Grid）

可以用来将游戏对象均匀地放置在其单元格中

#### 瓦片地图（Tilemap）

是网格的子游戏对象。由Tiles（瓦片）组成的。

#### 精灵（Sprite）

纹理的容器。大型纹理图集可以转换为精灵图集（Sprite Sheet）

#### 瓦片（Tile）

一种特殊的精灵。使用瓦片就像在画布上画画一样，画画时可以设置一些颜色和属性。

#### 调色板（Palette）

保存瓦片，将它们绘制到网格上

##### 工具栏：

###### 1.选择工具（Slect Tool）S

选择想要使用的瓦片，可以点击选择或拖拽多选选择，快捷键S

###### 2.移动工具（Move Tool）M

可以选择并移动瓦片位置，快捷键M

###### 3. 画笔工具（PaintBruch Tool）B

选择瓦片并在场景面板中绘制，快捷键B。

###### 4.方形区域填充工具（Fill Box Tool）U

选择一个或一片区域大小的瓦片，绘制区域小于选中区域时会部分绘制选中内容的纹理，等大区域时会1全部显示，大于则会平铺显示，快捷键U。

###### 5.取色工具（Picker Tool）I

取样选中瓦片并绘制，快捷键I。

###### 6.橡皮擦工具（Eraser Tool）D

擦去在场景中已绘制瓦片，快捷键D。

###### 7.填充工具（Fill Tool）G

大范围绘制选中的瓦片，快捷键G。

#### 笔刷（Brush）

用于将画好的东西绘制到画布上。使用Tilemap时可以在多个笔刷中任意选择，绘制出线条、方块等各种形状。

### 2.使创建的地形连续

##### 1.找到图片在Inspector面板更改每单位像素数

##### 2.切割精灵图集

选中一张精灵图集然后点击Sprite Editor

点击Slice选项Types选项中选择Grid By Cell Size（按照格子的方式切割）Grid By Cell Count（按行列切割）

### 3.渲染顺序与层级设置

#### 1.渲染

unity把物体显示出来

#### 2.层级（Layer）

可以在2D游戏物体中的**SpriteRenderer**和地形**TilemapRenderer**组件中的**Order in layer**属性中去设置层级的大小，**值越大，越后渲染，值越小，越先渲染，值大的游戏物体会覆盖值小的游戏物体。**	

#### 3.根据自定义轴向控制精灵的渲染

在项目设置中的摄像机设置里，将透明度排序模式改为自定义，然后根据需要改变透明度排序轴。（y为正则y值大的先渲染，y值小的会遮挡y值大的） 

#### 4.中心点与轴心点

SpriteRenderer中的Sprite Sort Point将中心点改为轴心点

轴心点：可以自定义的特殊点，充当精灵的“锚点”。**精灵以此为支点进行旋转**，坐标点位置则是指轴点心的位置

# 六、丰富游戏世界

### 1.预制体（Prefab）

是Unity中的一种特殊资源。预制体就是一个或者一系列组件的集合体，可以使用预制体实例化克隆体，后续可对克隆体属性进行统一修改。

### 2.预制体属性的修改和应用

# 七、Unity中的物理系统

### 1.添加组件

#### 1.刚体组件（Rigidbody）

使游戏物体能获得重力，接受外界的受力和扭力功能的组件，可以通过脚本或是物理引擎为游戏对象添加刚体组件

#### 2.碰撞器组件（BoxCollider）

使游戏物体具有跟挂载刚体组件的游戏物体发生碰撞能力的组件

#### 3.Tilemap Collider 2D组件

### 2.发生碰撞检测的条件

**双方必须都有碰撞器**，**且一方有刚体，最好是运动的一方**。因为Unity为了性能的优化，**刚体长时间不发生碰撞检测会休眠**（学至此处对于玩了这么多游戏的自己来说也算是初步揭开游戏开发的面纱了）

在此步骤后控制Ruby与箱子接触后会发生旋转，并且一直按住方向键后会发生抖动（控制脚本与刚体组件脚本代码产生冲突）

### 3.修复Ruby的旋转和抖动问题

1.调整碰撞器大小

2.在Rigidbody组件的Constraints中选择冻结z轴（于此解决旋转问题）

3.通过修改代码修改抖动问题

使用刚体控制Ruby的移动

```c#
private Rigidbody2D rigidbody2d;
//声明变量，变量类型Rigidbody2D，定义标签（名字）rigidbody2d（注意与类名区别）

rigidbody2d=GetComponent<Rigidbody2D>();
//获取指定类型的组件（必须是游戏物体上有的组件）
rigidbody2d.MovePosition(position);
//调用MovePosition方法并传入参数（position）
```

### 4.C#中的函数

#### 1.静态函数的调用：

**类名.函数名（参数）**，**全局可访问**，**不需要实例**

```c#
Input. GetAxis("Horizontal")
```

#### 2.普通（成员变量）函数的调用：

**对象名.函数名（参数）**，**需要实例**

```
rigidbody2d.MovePosition(position)
```

### 5.调整碰撞器

#### 1.可以通过调整碰撞器大小使游戏更逼真

#### 2.向场景（例如水）添加碰撞器

添加新的空的游戏对象加入碰撞器组件，将其拖至指定区域中并调整大小，产生碰撞效果。

#### 3.添加Tilemap Collider 2D组件

选中除水以外的资源将碰撞类型该为none

#### 4.添加Composite Collider 2D组件

将一个个方块的碰撞器联合到一起成为一个整体，避免地形卡住角色和出现缝隙的问题

# 八、道具的添加与交互

### 1.访问级别与访问修饰符

#### 1.访问级别

所有类型和类型成员都具有可访问级别，用来判断是否可以允许我们访问某些成员变量和方法。可使用访问修饰符来指定声明类型或成员的可访问性

#### 2.访问修饰符：

##### 1.public（公有的）：

任何代码均可以访问，应用于所有类或成员。（可以在外部访问，并在Inspector面板中直接修改值）

##### 2.private（私有的）：

只能在当前类中使用，应用于内嵌类或成员

##### 3.protected（受保护的）：

只能在当前类或其派生类中使用，应用于内嵌类或成员。

### 2.触发器与触发检测的条件

#### 1.触发器（Trigger）

触发某一个事件的开关

#### 2.制作触发器

在碰撞器组件中选择：是触发器

#### 3.触发检测的条件

与触发碰撞条件相似

1. 双方均挂载Box Collider组件
2. 两者之一必须是触发器
3. 有一方有刚体并最好是运动的一方

### 3.属性的定义与使用

使用属性可以提高代码安全性不会暴露在Inspector界面上

```c#
public int Health { get { return currentHealth; } }

if (ruByController.Health<ruByController.maxHealth)
```

### 4.伤害区域的制作

#### 1.bull类型

只存在true（1）和false（0）两种情况可以看作开关

#### 2.无敌时间

在受到伤害后会有一段无敌时间，此处用到计时器，在受到伤害后计时器开始在时间内不会受到伤害。

```c#

public float timeInvincible = 2.0f;//无敌时间常量
    private bool isInvincible;
    private float invincibleTimer;//计时器

if (isInvincible)
       {
           invincibleTimer = invincibleTimer - Time.deltaTime;
           if (invincibleTimer<=0)
           {
              isInvincible = false;
           }
       }

if (amount<0)
        {
            if (isInvincible)
            {
                return;
            }

            //受到伤害
            isInvincible = true;
            invincibleTimer = timeInvincible;
        }
```

#### 3.刚体休眠

刚体在一定时间内不运动会进入休眠

在刚体组件中打开永不休眠即可解决

### 5.敌人的制作

#### 1.敌人自己更换方向

计时器

```c#
//轴向控制
    public bool vertical;
    //方向控制
    private int direction = 1;
    //方向改变间隔，常量
    public float changeTime = 3;
    //计时器
    private float timer;
    
    timer -= Time.deltaTime;

        if (timer<0)
        {
            direction=-direction;
            timer = changeTime;
        }
        Vector2 position = rigidbody2d.position;

        if (vertical)//垂直轴向
        {
            position.y=position.y + Time.deltaTime * speed * direction;
        }
        else//水平轴向
        {
            position.x=position.x + Time.deltaTime * speed * direction;
        }
        rigidbody2d.MovePosition(position);
```

#### 2.敌人的碰撞检测

```c#
private void OnCollisionEnter2D(Collision2D collision)
    {
        RuByController rubyController = collision.gameObject.GetComponent<RuByController>();
        if (rubyController!=null)
        {
            rubyController.ChangeHealth(-1);
        }
    }
```

## 对下面这条语句还未理解透彻：

```c#
RuByController rubyController = collision.gameObject.GetComponent<RuByController>();
```

# 九、Unity中的动画系统

### 1.基本概念

#### 1.动画制作组件（Animator）

为了完成游戏对象动态效果的控制和创建，Unity为我们提供了一个动画设计解决方案，同时也是一个组件。

#### 2.动画控制器（Animator Controller）

根据当前游戏对象的状态控制播放对应的游戏动画。也可以叫做动画状态机。

#### 3.动画（Animation）

Unity中的动画资源，可以由动画控制器，代码去进行播放，也是一种组件。

### 2.操作流程

1.在游戏对象中添加Animator组件

2.创建AnimatorController资源并加入到组件中

3.window中添加Animation窗口以便观察（左侧为属性， 

### 3.Animation面板中操作

1.左侧为属性，右侧为每一帧

2.录制按钮可使动画属性在Inspector面板中改变录入不同帧时的值

3.将动画资源直接拖拽至Animation窗口中

4.全选后拉长至不同帧（自动等比缩放）可以使其动作变缓

### 4. Animator控制器面板

#### 1.Any State

任何状态，状态之间可以相互切换

#### 2.动画的过渡

动画之间的连线

#### 3.Entry（入口）

一旦游戏运行，直接走黄色的线，播放默认动画（不能设置任何条件）

#### 4.左侧

层级（Layers）：

让动画强制性播放如边跑步边射击

参数（Parameters）：

根据参数里面的参数列表来修改当前的transition根据transition可以进行状态的切换

### 5.让游戏对象状态切换平滑

1.关闭退出时间

2.将过渡持续时间调为0

### 6.混合树的使用方式和意义

#### 1.混合树（Blend Tree）

用于允许通过按不同程度组合所有动画的各个部分来平滑混合多个动画。各个运动参与形成最终效果的量使用混合参数控制，该参数只是与动画器控制器关联的数值动画参数之一。要使混合运动有意义，混合的运动必须具有相似性质和时间。混合树是动画器控制器中的特殊状态类型。

#### 2.转换（Transition）

用于在给定时间量内从一个动画状态（Animation State Machine）的一部分。如果转换迅速，则通常可从一个运动很好地转换为完全不同的运动。

#### 3.创建混合树

右键Animator右侧面板点击From New Blend Tree

#### 4.混合树的使用

1.添加Motion

2.向Motion中添加Animation Cilp

### 7.Ruby的动画控制器

ps：在Parameters中设置speed并在conditions中为其赋一定值即可令其移动和停止更加平滑（在设计宠物过程中要注意）

GetComponent语句可以调用不同脚本的函数，但调用完后需要封装至一个容器中

ps：游戏初始化start函数不运行，在下一帧才运行。解决：将子弹脚本的start函数改为Awake（唤醒）函数（在start函数之前调用，并在游戏物体实体化后立刻去调用）

### 8.子弹的发射功能

#### 1.层级（Layer）

注意渲染层级（组件中的属性）与层级（内置的系统或是功能）

可以防止同一层级造成子弹碰撞不正确，可以自己设置层级并控制不同层级是否发生碰撞

#### 2.创建子弹脚本

#### 3.定义Launch函数来发射

### 9.修复机器人的方法

ps：空引用报错与问题修复

1.通过定义broken函数来判断机器人的状态

2.若为true则可进行移动的脚本

在与子弹接触后bool变为false不进入start函数进入Fix函数

3.在子弹脚本中也要调用敌人控制脚本来检测状态

4.制作并添加机器人修复的动画，并添加下面代码进入Fixed函数

```c#
animator.setTrigger("Fixed")//与动画器对应
```

# 十、导入Cinemachine工具包

### 1.导入CineMachine

窗口栏中的包管理加入

### 2.创建虚拟相机

### 3.镜头跟随

#### 1.将Ruby放入follow中即可

#### 2.镜头跟随的限制边界

再virtual camera中的add extension中选择

cinemachine confiner

添加多边形碰撞器（Polygon Collider 2D）

# 十一、粒子系统

粒子系统在交互运动中主要用于效果，会产生几个或者几百个小粒子，具有方向、寿命、大小、颜色或其他类型的一些小图像。使用粒子集体创建一些效果

## 项目区右键创建效果

### 1.纹理表格动画

1.将模式改为Sprites

2.添加精灵

3.开始帧设置为双常数间随机并设置值为0和2

4.将随时间位移的帧调为零

### 2.形状

1.改变发射角度

2.改变半径

### 3.基础属性

1.生命周期时间（粒子的在屏幕中显示的时间）

2.开始大小

3.开始速度

4.调整生命周期内颜色以达渐变至消失的效果

5.调整生命时间内大小

6.设置烟雾不跟随效果（将模拟空间改为世界）

### 4.设置修好后烟雾消失

创建一个新方法将粒子系统赋值进去，在修复函数中加入停止粒子的语句。

```c#
public ParticleSystem smokeEffect;

public void Fix()
    {
        broken = false;
        rigidbody2d.simulated = false;
        animator.SetTrigger("Fixed");
        smokeEffect.Stop();
    }
```



### 5.打击特效

# 十二、Unity中的UGUI

### 1.UI

玩家与应用程序交互的界面（例如血条，装备栏，技能）

### 2.UGUI

Unity中封装的一套UI系统 

### 3.创建

在项目栏中右键在UI中选择Canvas（必须是Canvas的子对象才能渲染）

### 4.Canvas渲染模式

#### 1.覆盖

在最顶层渲染

#### 2.摄像机

随着摄像机移动

#### 3.世界空间

例如游戏角色头顶血条

### 5.Canvas Scaler组件

根据屏幕情况进行缩放（自适应）

#### UI缩放模式

##### 1.恒定像素大小

无法根据UI大小改变

##### 2.屏幕大小缩放

根据屏幕大小缩放较为智能，但是像素大小是固定的，可能会导致模糊

##### 3.恒定物理大小

### 6.射线检测组件

### 7.Ruby血槽制作

UI不是以Unity单位为单位的

1.创建image将血槽精灵赋值进去，调整轴心点与锚点。

2.基于父对象UI的拉伸缩放：将锚点拉伸包裹住子对象

### 8.Ruby血条制作

1.头像在血条后可使渲染顺序改变

2.创建Mask组件，并关闭显示遮罩图形

### 9.创建UIHealthBar脚本

# 十三、Unity中的射线检测

### 通过方法来检测与碰撞体发生交互

### 1.创建对话框

### 2.创建脚本

# 十四、游戏音效与音乐的添加

### 1.Audio Listener组件

在摄像机上（若多个摄像机则只需一个）接收音乐的组件

### 2.Audio Source（音频源）

播放音乐的组件

### 3.创建

创建空对象，添加Audio Source组件

# 十五、任务系统

在对话框出现后，Ruby可以发射子弹

# 十六、打包

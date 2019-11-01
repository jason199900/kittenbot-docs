# 青蛙手柄分栏积木块

## 成功加载青蛙手柄分栏，并连接上

如下图，出现绿色的勾勾图标，就证明串口已经正确连接上了

![](./images/c03_01.png)

## 手柄按键与金手指检测积木块

![](./images/c03_02.png)

### 使用示例1——xy按键按下播放蜂鸣器音乐

确保青蛙手柄的串口已经连接上，否则板上的蜂鸣器不会响。

**操作与结果：**按下X或者Y按键，蜂鸣器就会响起音乐来。

![](./images/c03_12.png)

### 使用示例2——摇杆左右控制小猫移动

手柄摇杆左右可以控制舞台小猫左右移动

问：摇杆能否读到模拟值？

答：不能，因为如果摇杆涉及读到不同模拟值，对应Scratch角色运动控制比较麻烦。本手柄主要针对初学者入门，所以摇杆没有做读模拟值

**操作与结果：**左右摇动下摇杆，观察小猫会在舞台随着摇杆左右移动

![](./images/c03_13.png)

### 使用示例3——摇杆按下

摇杆除了可以上下左右摇动，还有一个确认按钮(就是直接按下摇杆)。所以这里特意做了一个示例用来说明摇杆按键。

**操作与结果：**当你按下摇杆杆件，舞台小喵会说出“摇杆按键按下”，两秒后文字消失，再按下时候，重新说出“摇杆按键按下”

![](./images/c03_14.png)

### 使用示例4——金手指触摸

青蛙手柄其中一个很好玩的功能就是——金手指触摸。金手指触摸还可以通过鳄鱼夹连接到各种水果上或者金属的物体上。

**操作与结果：**当金手指1、2分别被手摸的时候，舞台会对应显现角色A和角色B(当然你也可以连接8个鳄鱼夹，刚好做出一个水果琴)

![](./images/c03_19.png)

![](./images/c03_15.png)

## 金手指独立检测积木块

![](./images/c03_03.png)

此积木块的功能实际等同**当按键XX按下**，只是为了方便大家对金手指进行音调编程，所以特意做了一个独立的积木块。

这样大家对这Do、Re、Mi这些字符来编程比较容易对应上。

![](./images/c03_16.png)

## 蜂鸣器音调设置积木块

你可以自由设置蜂鸣器的音调和时间

![](./images/c03_04.png)

### 使用示例1——xy按键按下播放蜂鸣器音调

确保青蛙手柄的串口已经连接上，否则板上的蜂鸣器不会响（串口驱动之前已经提前安装好了）

**操作与结果：**当按键x与y分别被按下时，蜂鸣器会发出不同的声响。

![](./images/c03_17.png)

## 蜂鸣器音乐设置积木块

音乐播放内置了Microbit的常规音乐

![](./images/c03_05.png)

### 使用示例1——xy按键按下播放蜂鸣器音乐

确保青蛙手柄的串口已经连接上，否则板上的蜂鸣器不会响

**操作与结果：**当按键x与y分别被按下时，蜂鸣器会发出不同的短曲音乐

![](./images/c03_12.png)

## 红外特定编码发射积木块

红外编码使用这个需要注意下，这个红外编码是指常规的NEC编码（采用16进制编码）

举个例子：电视遥控器某个按键红外发出去的编码有可能是"01ABCDEF",可以看到这个编码一定是8个字符组成的，字符的范围（0~9，A~F，16进制）。**所以如果编码的字符串在这些字符范围以外的，程序必然是错的！**
 
![](./images/c03_06.png)

### 使用示例1——xy按键按下发送红外编码

**操作与结果：** 按x按键，发送12345678这个红外编码，按y按键发送87654321这个红外编码

![](./images/c03_18.png)

## 红外接收触发积木块

只要青蛙手柄上的红外接收器接收到红外编码（无论是怎样的红外编码），这个帽子积木都会进行触发

![](./images/c03_07.png)

**操作与结果：**当青蛙手柄的红外接收管，接收到红外信号，这个帽子积木块边缘就会发亮（因为发亮是一瞬间，太难截图了，大家理解下）

## 红外解码内容积木块

![](./images/c03_27.png)

光接收数据是不行的，我们需要接接收的数据的进行判断。例如家里的遥控器都是很多个按键，每个按键对应不同的红外编码，对应触发不同的事件（例如电视喇叭声音变大，或者换台等等）

![](./images/c03_08.png)

一般我们会将红外解码数据前面的勾勾勾上，这样就可以在舞台左上角可以看到，即时接收回来的红外数据

![](./images/c03_09.png)

![](./images/c03_10.png)

## 红外解码后发射同样的内容

因为我们已经把遥控器对应的按键红外码解出来了，这时候，我们对应把发射红外的发射出去。

这样就成功把遥控器上的按键复制下来了。

![](./images/c03_28.png)

## 3PIN模块（背后的端口3与端口4）

![](./images/c03_11.png)

### 数字写（以LED模块为例）

端口写，适用于逻辑电平的输入模块，如LED模块

Port3口 接好LED模块

![](./images/c03_20.png)

程序：

![](./images/c03_23.png)

**实验结果：** LED模块每隔一秒闪一下


### 数字读（以按键模块为例）

使用的按键模块，按下是低电平，平时是高电平

![](./images/c03_22.png)

程序：

![](./images/c03_24.png)

**实验结果：** 当按键按下时（低电平），小猫在思考，嗯....,否则一直说你好

### PWM写（以舵机为例）

舵机是典型的被PWM写的器件，我们可以控制舵机的角度

舵机这边因为没有做特意的转接线，所以只通过公转公杜邦线转接一下，舵机接到port3端口

![](./images/c03_29.png)

程序：

![](./images/c03_26.png)

### PWM写（以LED模块控制亮度为例）

![](./images/c03_20.png)

程序，通过变换PWM值，可以控制LED的亮度

### 模拟读写（以电位器模块为例）

![](./images/c03_21.png)

程序：

旋动电位器，观察舞台小猫说出来的值，通过模拟值的大小变化，我们可以结合Scratch舞台做些好玩的项目

![](./images/c03_25.png)
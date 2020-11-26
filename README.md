
## 概念

命令行界面（Command-Line Interface，缩写：CLI）：在图形用户界面得到普及之前使用最为广泛的用户界面，它通常不支持鼠标，用户通过键盘输入指令，计算机接收到指令后，予以执行。也有人称之为字符用户界面（character user interface, CUI）

图形用户界面（Graphical User Interface，缩写：GUI）：采用图形方式显示的用户界面。在视觉上更易于接受，学习成本大幅下降，也让电脑的大众化得以实现

Fn 键：在紧凑布局中以组合键方式定义一键两义的按键

PCIe：一种高速传输的串行总线

[屏幕](https://github.com/xin113726/computer/issues/1)

[显示器](https://github.com/xin113726/computer/issues/2)

[硬盘](https://github.com/xin113726/computer/issues/3)

## 数据传输

Bps（Bits per Second）：数据传输速度的常见单位。bit 表示位或比特，是信息技术存储中最小的单位。

Kbps（比特率）：指的是数字信号的传输速率，就是每秒钟传送多少个千字节的信息

```
B = Byte

b = bit

8b = 1B（8 位等于 1 字节）

1024 Kbps = 1 Mbps
```

**带宽**

- Mbps = Mbit/s，即兆比特每秒

- Gbps = Gbit/s，即千兆比特每秒

USB Type C（USB 3.1 Gen2 Type C）：采用了 Type C 接口规格，支持最高 100w 的 PD 充电协议，传输速率最高 10Gbps

雷电3（Thunderbolt™3、雷雳3）：采用了 Type C 接口规格，支持最高 100w 的 PD 充电协议，传输速率最高 40Gbps，可以外接显卡

流量：用户上网发送和接收的数据量总和

## 网络

光猫：千兆

网线：超五类、六类、超六类、七类

路由器：WIFI6、Mesh

端口聚合

## 内存

标准频率（产商标注）：忽略外部因素的保底频率

主板不超频的情况下，内存条工作频率下线取决于标准频率，上限取决于内存条本身的颗粒体质和 cpu 默认内存频率两者之间较低的值决定；内存超频后，上限由内存体质、IMC（内存控制器）体质/性能、主板布线与电气性能这三者最低的值决定

cpu 默认内存频率：主板不超频的情况下，该 cpu 支持的最大内存频率

### 电脑卡顿问题

CPU 和内存交互数据

换固态：加快硬盘读写速度

加内存：存储更多数据

## 显卡

Turing 架构

win10系统通过显卡去读取显示器驱动板的 EDID 信息来获取显示器的分辨率、刷新率、型号

## 电源

插座提供的市电：220V 50Hz 的交流电

电源：把高压的交流电转换成直流电，再输出给各个配件

电脑需要独立供电的设备：CPU、主板、显卡、硬盘

非模组电源：所有接口都直接从直流输出端拉出来，无法自行去除的电源

全模组电源：整个电源的所有线缆都以接口的形式存在，需要什么线就接什么线

## 帧数、刷新率

帧数：显卡一秒钟渲染好并发送给显示器多少张画面

刷新率：显示器逐行扫描画面的速度

在电脑里，帧是由显卡去渲染出来的（60FPS 表示显卡一秒画出 60 张画面），然后发送给显示器。
显示器接收到帧以后，通过逐行扫描显示在面板上，从左上角开始一行一行地进行绘制，一直绘制到屏幕的右下角，一幅完整的帧就被显示出来了。
然后显示器将扫描点挪回左上角，这个重置扫描点的过程称为 VBlank
VBlank 结束以后会从左上角继续逐行扫描下一帧，如此循环往复

逐行扫描的速度就是屏幕刷新率
60Hz 的屏幕意味着一个屏幕可以在1秒钟之内进行完整的60次全画幅的逐行扫描
所有刷新率越高的屏幕所能表现出来的帧数越多，画面延迟越低，画面越流畅

不同画面对应显卡本身的运算压力不同，所以帧数会一直在变，而显示器的刷新率是固定的。为了让一个波动的输出帧能匹配固定的刷新率，就要设置帧缓存

帧缓存 Frame Buffer：默认有前缓存和后缓存。显卡渲染完一帧后，先写入后缓存，然后前后缓存发生交替（帧传递 Buffer Swap），后缓存变成了前缓存，发送给了显示器

画面撕裂：帧率与刷新率不匹配

延迟：帧率大于刷新率，显卡渲染好的画面不能立刻反馈到屏幕上，会产生画面延迟

卡顿：帧率小于刷新率，显示器重复显示上一帧画面，会产生画面卡顿

垂直同步：显卡等显示器，强制同步帧率和刷新率

VRR（自适应显示器刷新率）：显示器等显卡，强制延长 VBlank 时间，让显示器持续显示上一帧，等到显卡绘制完成后，再发生帧传递。
应用：G-sync 和 Free-sync 

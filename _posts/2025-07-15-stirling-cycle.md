---
layout: post
title: "Stirling cycle"
subtitle: "斯特林热机，制冷机及热泵"
date: 2025-07-15
author: "Paraselene"
header-img: "img/post-bg-2015.jpg"
tags: []
---

# 项目：斯特林热泵的应用

## 1.背景知识

### 1.1 斯特林循环

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-15-21-12-18-image.png)<img title="" src="file:///D:/Paraselene_Blog/Paraselener.github.io/img/2025-07-15-21-13-18-image.png" alt="" width="340">

斯特林循环是一种描述斯特林装置所使用的热力学循环。该循环最早用于罗伯特・斯特林于 1816 年在其兄弟的帮助下发明、开发并获得专利的原始斯特林发动机。

如图所示，该循环由两个**等温**以及两个**等容**过程所构成。

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-15-21-17-30-image.png)

1-2：**等温膨胀过程**    （工质从高温热源吸热，同时膨胀做功，该过程保持温度不变）

2-3：**等容放热过程**    （工质保持体积不变，同时向外放热）

3-4：**等温压缩过程**    （工质向低温热源放热，体积减小，保持温度不变）

4-1：**等容吸热过程**    （工质保持体积不变，同时吸收热量）

1-2-3-4的循环过程为热机循环。该循环的热量以及功量计算如下：

1. 1-2（等温膨胀）该过程所吸收的热量全部转化为功。
   
   $$
   W=-\int_{V_1}^{V_2}pdV=-nRT_hln\frac{V_2}{V_1}
   $$
   
   $$
   Q_{in}=-W
   $$

2. 2-3（等容放热）该过程体积不变，功量为0，向外放热，内能减小。
   
   $$
   W=0
   $$
   
   $$
   Q_{out}=nC_v(T_h-T_l)
   $$

3. 3-4（等温压缩）该过程与1-2相反，功全部转换为热传递给低温热源
   
   $$
   W=-nRT_lln\frac{V_1}{V_2}
   $$
   
   $$
   Q_{out}=-W
   $$

4. （等容吸热）该过程体积不变，功量为0，吸热后内能增加。
   
   $$
   W=0
   $$
   
   $$
   Q_{in}=nC_v(T_h-T_l)
   $$

热机效率的计算公式为：

$$
\eta=\frac{W}{Q_{in}}=\frac{R(T_h-T_l)ln\frac{V_2}{V_1}}{C_v(T_h-T_l)+RT_hln\frac{V_2}{V_1}}
$$

注意到，2-3过程放的热量和4-1过程所吸收的热量具有相同的数值大小。如果有一种装置可以收集2-3所放的热，之后再将这部分热量传递给4-1过程，那么，2-3和4-1过程便不需要额外的热源，两个过程的吸放热可以在**内部**被消化。

<u>该装置就是蓄热器（也称为回热器）</u>

对于理想的斯特林循环。假设蓄热器具有100%的效率，那么该循环的热机效率即为：

$$
\eta=\frac{W}{Q_{in}}=\frac{R(T_h-T_l)ln\frac{V_2}{V_1}}{RT_hln\frac{V_2}{V_1}}
=\frac{T_h-T_l}{T_h}=1-\frac{T_l}{T_h}
$$

**理想的斯特林循环具有和卡诺循环相等的效率，该效率只和高低温热源的温度有关。**

下图是斯特林循环和卡诺循环的T-S和P-V图

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-15-22-02-16-image.png)

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-15-22-02-24-image.png)

斯特林循环有几个关键点：

- 等温过程：等温意味着**无温差传热**，这需要无穷大的散热面积和无限长的散热时间，导致压缩过程的转速不能提高，否则就会变成绝热压缩（热量来不及传递）；

- 蓄热器：蓄热器将2-3和4-1过程的传热变为**内部换热**，从而降低整个循环的不可逆程度，提高蓄热器的效率对整个循环的效率很重要；

- 可逆：整个循环是可逆的，这意味着如果输入机械功，则斯特林机械可以作为**制冷剂和热泵**工作。

### 1.2 斯特林制冷循环和蒸汽压缩制冷循环

**蒸汽压缩制冷循环**是目前商用制冷和制热所常用的循环，下表简单总结了二者的区别：

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-16-21-00-38-image.png)

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-16-21-00-47-image.png)

|       | 斯特林制冷              | 蒸汽压缩制冷          |
|:-----:|:------------------:|:---------------:|
| 制冷原理  | 气体压缩与膨胀            | 相变吸热            |
| 压缩过程  | 等温                 | 等熵              |
| 工质    | He，H<sub>2</sub>   | 氟利昂             |
| 组件    | 动力活塞，配气活塞，蓄热器，热交换器 | 压缩机，热交换器，膨胀阀，阀件 |
| 应用    | 低温（最低可达10K）        | 住宅              |
| 系统复杂度 | 复杂，紧凑              |                 |
| 效率    | 低                  | 高               |

### 1.3 工质的选择

斯特林循环的工质一般选择氢气和氦气，高的导热率和低的摩尔质量有利于快速传热

## 2. 斯特林机器结构

常见的驱动机构分为三种：机械驱动，自由活塞，脉冲管制冷机。

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-16-21-53-53-image.png)

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-16-21-54-21-image.png)

脉冲管制冷机不在本文的讨论范围。

- 机械驱动用于大功率的场合

- 大多数的低温制冷机使用自由活塞结构，自由活塞的缺点是：配气活塞的运动难以预测，因此性能易被影响

机械驱动的主要缺点是摩擦损耗以及润滑密封，自由活塞的优点是无需接触密封（使用气体轴承），高效率的直线电机，易于调节功率等。

斯特林机器常见的有三种结构：阿尔法，贝塔，伽马。

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-16-22-12-52-image.png)

可以看出，斯特林机器一般具有几个部件：气缸，两个活塞，蓄热器，热交换器。

配气活塞是一种特殊用途的活塞，用在Beta和Gamma机器中移动气体，他可以密封也可以不密封在气缸中。

- Alpha：两个活塞，一个位于热端，一个位于冷端。垂直排列连接在曲轴上，形成90°的相位差

- Beta：一个气缸，包含一个动力活塞和一个配气活塞，曲轴上形成90°的相位差

- Gamma：两个气缸,包含一个动力活塞和一个配气活塞，由于是两缸分离的结构，因此可以同时制冷和制热，比如饮水机。

### 2.1 Alpha-Type（热机）循环过程详解

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-16-22-29-19-image.png)![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-17-21-16-19-image.png)

1-2过程：从图中可以看出，大部分的工质留在热缸，从0-90°时，气缸容积变大，气体膨胀吸热；

2-3过程：此时，热缸压缩，冷缸膨胀，容积近似不变，工质从热缸往冷缸流动，蓄热器吸收热缸的热；

3-4过程：热缸和冷缸同时压缩，不过大多数的工质留在冷缸，近似等温压缩（低温）；

4-1过程：冷缸压缩，热缸膨胀，容积近似不变，工质从冷缸流向热缸，吸收蓄热器的热量。

### 2.2 Beta-Type（制冷机）循环过程

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-17-21-46-28-image.png)

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-17-21-46-41-image.png)

Beta型的机器也具有类似的循环，区别在于，它是由电机驱动的，并且具有配气活塞和弹簧等独特结构。

## 3. 目前的斯特林机应用现状

### 斯特林低温制冷应用：

- 由于 20 世纪中叶以来对低于 120 K 的低温的需求日益增长，人们进行了大量研究，并在广泛的应用领域取得了成果。

- 斯特林制冷机在低温范围内已经建立良好，并被认为是微型闭合循环系统的首选。

- 使用斯特林循环的设备制造成本仍然很高，这是由于生产量有限，以及工作条件需要特殊材料和相对较高的技术。

### 斯特林中温制冷应用：

- 使用斯特林循环机制冷很少用于家用或商业制冷的中温环境。

- 已在家用冰箱中运行的蒸汽压缩式冰箱接近完美状态，开发其他制冷系统的必要性有限。

- 这些机器理论上效率最高，因此成为现有蒸气压缩制冷系统的潜在替代品。

### 斯特林热泵应用：

像中温制冷一样，目前还没有商业公司生产斯特林热泵，科学机构正在进行更多的研究。

## 4.斯特林低温制冷机的应用

本项目的主要目的是探讨斯特林机器在HVAC行业的应用，因此未查找斯特林发动机的相关文献。

在斯特林循环商业应用的寻找中发现，目前的商用机器都集中在低温制冷。下面将介绍笔者所搜集的部分斯特林制冷机的应用

### 4.1 应用的领域

斯特林制冷机的应用集中在低温制冷区域，因此大部分需要低温制冷的场景都可以找到它的身影。

- 液化气体
  
  - 液化天然气
  
  - 液氢，液氮的生产

- 生命健康
  
  - 血液，细胞组织，病毒等的保存
  
  - 核磁共振磁铁的冷却
  
  - 医用氧气（液氧）

- 超导领域
  
  - 电力系统的运输
  
  - 故障电流限制
  
  - 旋转设备
  
  - 超导磁铁

- 食品饮料
  
  - 食物冷冻
  
  - 液氮剂量

- 航空航天
  
  - 液态氢
  
  - 液氧
  
  - 空间模拟舱
  
  - 超导

- 科研机构
  
  - 核物理学
  
  - 仪表冷却
  
  - 放射性测量
  
  - 液氩中微子探测器

以上关于茨特林低温制机器的资料来自于荷兰的[STIRLING CRYOGENICS]([https://stirlingcryogenics.com/](https://stirlingcryogenics.com/))公司，基本涵盖了目前的斯特林制冷的所有应用场景。

### 4.2 斯特林制冷机产品

下面所展示机器的规格参数局势从这些厂家的官网下载的，不再具体介绍，感兴趣的可以从这些链接中自行查看。

#### [STIRLINGCRYOGENICS]([https://stirlingcryogenics.com/](https://stirlingcryogenics.com/))

**DS-SPC-1机器参数：**

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-19-17-39-07-image.png)<img title="" src="file:///D:/Paraselene_Blog/Paraselener.github.io/img/2025-07-19-17-39-16-image.png" alt="" width="460">

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-19-17-39-52-image.png)

**DS-SPC-4机器参数：**

<img title="" src="file:///D:/Paraselene_Blog/Paraselener.github.io/img/2025-07-19-17-40-37-image.png" alt="" width="374"><img title="" src="file:///D:/Paraselene_Blog/Paraselener.github.io/img/2025-07-19-17-40-43-image.png" alt="" width="273">

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-19-17-41-18-image.png)

**[SunPower]([https://www.sunpowerinc.com/](https://www.sunpowerinc.com/))**

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-19-17-46-18-image.png)

这是Sunpower公司的产品介绍视频：[How Does a Sunpower Stirling Cryocooler Work? Sunpower Free-Piston Stirling Cryocooler Animation](https://www.youtube.com/watch?v=ZSJFPb8030g)

[**Stirling ULTRACOLD**]([https://www.stirlingultracold.com/](https://www.stirlingultracold.com/))

**ULT25NEU**

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-19-17-52-59-image.png)<img src="file:///D:/Paraselene_Blog/Paraselener.github.io/img/2025-07-19-17-53-08-image.png" title="" alt="" width="339">

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-19-17-53-22-image.png)

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-19-17-53-30-image.png)

**VAULT100™**

<img src="file:///D:/Paraselene_Blog/Paraselener.github.io/img/2025-07-19-17-54-24-image.png" title="" alt="" width="189">![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-19-17-54-31-image.png)

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-19-17-54-43-image.png)

![](D:\Paraselene_Blog\Paraselener.github.io\img\2025-07-19-17-54-49-image.png)

国内的斯特林制冷机厂商有[华斯特林]([https://chinastirling.com/](https://chinastirling.com/))公司，宁波钜心公司，海尔生物等，不再一一赘述。

相关的信息可通过官方网站搜寻。

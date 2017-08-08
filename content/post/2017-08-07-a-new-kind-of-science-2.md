+++
date = "2017-08-07T23:45:43+08:00"
title = "一种新科学(2)"
tags = ["读书笔记", "科学"]
keywords = ["Wolfram", "细胞自动机"]
+++

## 摘要

本文是我在[上次挖坑](/post/2016-03-20-a-new-kind-of-science)之后读完沃尔夫勒姆的著作《一种新科学》后的一些感想。
《一种新科学》是一本贡献和争议并存的书籍，它深入的探讨了元胞自动机的演化，也即计算复杂性而非传统科学方法中数学公式的复杂性，作为宇宙本质的一种可能性。
本文简述了该书的成书背景和内容，探讨了争议和贡献的部分。
《一种新科学》虽然是一种视野的开阔，但是离颠覆现有的科学研究方法还相去甚远。

## 背景介绍

《一种新科学》是斯蒂芬·沃尔夫勒姆的一本长篇巨著。
在2002年5月14日发行之后的一个星期里，《一种新科学》初版五万册就全部销售一空，在亚马逊排行榜上一度高居榜首，成为2002年夏天最畅销的书。

作者斯蒂芬·沃尔夫勒姆1959年出生于伦敦，父亲是相当成功的作家，母亲是牛津大学的哲学教授。
他幼年聪慧，13岁入伊顿公学，15岁发表首篇粒子物理方面的学术论文。
在获得牛津大学的奖学金并在牛津学习一年之后，即到了美国阿格纳国家实验室的理论高能物理小组工作。
1978年19岁的沃尔夫勒姆受著名物理学家穆雷·盖尔曼之邀去到加州理工学院，从事基本粒子物理学方面的研究，取得显著成就，一年内获得理论物理学博士学位。
1980年沃尔夫勒姆成为加州理工学院一员，与费曼共事。
1981年被授予麦克阿瑟“天才人物”奖，并成为该奖最年轻的获得者。之后他又到了爱因斯坦度过后半生的普林斯顿高级研究所工作，再后来又成为伊利诺斯大学的物理学、数学和计算机科学教授。

1986年27岁的沃尔夫勒姆创立了以他的姓氏命名的沃尔夫勒姆研究公司，成为一位企业家。
1988年他的公司发布了Mathematica，一种科学计算软件。
由于其先进的符号计算理念，成为最广泛使用的数学软件之一。
沃尔夫勒姆也因此实现了财务自由。

其实早在1981年的时候，沃尔夫勒姆就对自然界复杂性起源这一命题产生了兴趣，但是由于研发Mathematica和忙于公司事物，这一兴趣一直被搁置。
90年代初，在Mathematica第二版发行后，公司也渐渐步上正轨。
沃尔夫勒姆便将自己的几乎全部时间都投入了研究和陪伴家人中。在新世纪的开端，百万行代码之后，这些成果变成了1200多页的长篇著作《一种新科学》。

除了畅销之外，沃尔夫勒姆还声称《一种新科学》是科学史上最为重要的一部著作，而他所做的一切不亚于牛顿的贡献。
这种豪言壮语自然十分吸引我去一探究竟。
于是在一个假期里读完了这本大部头。

## 内容简介

全书围绕元胞自动机这一核心概念进行展开。
元胞自动机是由上个世纪50年代乌尔姆和冯·诺伊曼为了研究机器人自我复制的可能性提出一种离散型动力系统。
元胞自动机是研究复杂系统行为的最初理论框架，也是人工智能的雏形。

设想一个平面上纵横相交的许多直线构成了许多网格，每一个网格就是一个元胞。
这些元胞可以具有一些特征状态，譬如被染成黑、白、红、绿等颜色。
在每个特定的时刻每个元胞只能处于一种特征状态中。
随着时间的增加，或者叫做叠代过程的进行，每个元胞根据周围细胞的状态，按照相同的规则自动地改变它的状态。
这就构成了一台元胞自动机。

一个元胞自动机可以由四个参数唯一决定：

1. 元胞活动的空间维度数
1. 元胞可能具有的状态集合
1. 元胞改变状态的规则
1. 元胞自动机中各元胞的初始状态

书中主要考虑空间维度为一维的元胞自动机，元胞可能具有的状态只有两种，用颜色表示成黑色或白色，一个元胞只根据自己的状态和相邻的两个元胞的状态来改变自己的状态。
可以很容易计算出这样的一维元胞自动机的规则数有\\(2^8=256\\)种。

![图1：110号元胞自动机规则及20步后的状态](/images/2017-08-07-a-new-kind-of-science-2/rule110_20.png)

![图2：110号元胞自动机250步后的状态](/images/2017-08-07-a-new-kind-of-science-2/rule110_250.png)

如图1所示，上面是第110（二进制表示\\(01101110_2\\)）号元胞自动机的规则，下面是其20步之后的状态（0代表白，1代表黑），初始状态为一个黑色元胞。
20步时一切似乎都还跟规则一样简单有规律。
但是如图2所示，250步之后，一些结构开始既不是周期性地也不是完全随机地出现在画面上。

沃尔夫勒姆探索了这256种元胞自动机，以及更高维的2维和3维的情况，发现复杂性增加了但是模式类似。他将元胞自动机划分为四种模式：

1. 只生成简单重复的图案，比如全黑、全白、或黑白相间如国际象棋棋盘等等
1. 产生一些自相似的分形图案，形成稳定的嵌套结构
1. 产生的图案具有明显的随机性
1. 产生的图案既不是规则的也不是完全随机的复杂图案。它们呈现出某种有序性，但却不能被预测。

第四类元胞自动机是沃尔夫勒姆最感兴趣的，而规则30号和110号则是其中最有代表性的。

书中将随机分为了三类：一是每一步输入都随机结果随机，二是初始输入随机结果随机，如混沌效应，三则是系统内在的随机性，与输入无关。
第四类元胞自动机即是这类。甚至Mathematica的伪随机数生成器都是用30号元胞自动机实现的。
而自然界的许多现象也是如此，那么这种元胞自动机和自然现象有什么关系呢？

一方面来看，宏观上看似连续的事物微观上可能是离散的，比如水流和空气在微观尺度下都是一个个分子。
另一方面，在1994年，数学家马修·库克证明了110号元胞自动机是图灵完备的。
所谓图灵完备即是说它能像计算机一样完成所有的计算任务。

之后的几章里，沃尔夫勒姆用元胞自动机完成了乘法、除法运算，和求素数、求平方根、求π值，甚至解偏微分方程。
并把一维元胞自动机扩展到多维元胞自动机，产生更高的复杂程度，模拟了雪花、生物细胞等等。

更进一步，弹子球、纸牌游戏、布朗运动、三体问题等等问题中的随机性都可以用元胞自动机来解释；
流体的湍流、晶体生长的规律、华尔街股票的涨落也都可用元胞自动机来模拟；
还有自然界中的树叶、贝壳、生物色素沉着等，元胞自动机能生成与它们一模一样的图案和形态。

传统科学在解释这些问题上展示了惊人的复杂性，有些问题甚至不能很好的解释，而沃尔夫勒姆用元胞自动机简单直接的解释了这一切。

之后，他试图使用元胞自动机来解释整个宇宙，认为宇宙就是一个元胞自动机，从简单的规律中产生复杂性。

## 同行对《一种新科学》的一些评价

在《一种新科学》出版之后，由于其畅销和沃尔夫勒姆可以称之为狂妄的一些论调，很多科学家也对这本书发表了自己的评价。

对生物学，事实上沃尔夫勒姆所举的只是一些有限的简单的生物学例子，就得出结论说许多生物体上的差异最终几乎都与自然选择无关，有点过于武断。
也有人批评作者缺乏必要的生物学知识，而元胞自动机也从来没有产生出一种比一条蚯蚓更复杂的生物来。
或许应该肯定沃尔夫勒姆在《新科学》里给出了一些好的事例，它们说明自然选择学说还不能解释某一种生物体上的复杂特征。这属于科学，但不是新的。
生物学家们知道得很清楚，自然选择学说不能预言某一匹斑马身上的特殊条纹，就好比物理学家们知道通过解算微分方程不能预测一年之后的天气。

复杂性和随机性可谓此书的中心论题，但是沃尔夫勒姆一直不对它们作出严格的定义，直到后面才稍稍正面论及它们。
沃尔夫勒姆是从观察者对复杂系统的感觉如何，而不是从复杂系统本身如何产生，来定义复杂性和随机性。
也就是说，它看上去是复杂的，它就是复杂的。

[同时，沃尔夫勒姆这种闭门造车不经同行评议就出书，以及受到前人工作启发但是并没有引用其文献的做法也招致了批评](https://arxiv.org/abs/quant-ph/0206089)。

实际上书中的许多观点前人或多或少都有过研究。
著名物理学家费曼曾表达过宇宙是离散的而非连续的观点。
而弗雷德金，计算物理学的先驱也表达过世界的本质是计算这种类似的观点。

在接受《福布斯》记者采访时沃尔夫勒姆作出了他的大胆预言：“50年内，更多的技术，将基于我的科学而不是传统科学，被创造出来。
人们在学习代数之前将先学元胞自动机理论”。

为了更好的评价沃尔夫勒姆的工作，我想先来回顾一下传统科学到底是怎么运行的。

## 现有的科学方法

### 科学方法的历史

所谓科学方法，就是一种可以生产科学的过程。
科学的强大之处就在于可以在前人知识的基础上，对一个话题进行更加复杂的研究和探讨，建立更加深入的理解。
这一模型让人类可以延续几千年的知识积淀，使得社会可以持续的进步和发展。
而这一模型来之不易，经过了千年的发展。

[早在千年之前伊拉克学者海什木就在自己的实验物理学研究著作《光学书》里，指出提出问题并且依次验证它们对科学方法的重要性，因而被视为科学方法的先驱](https://en.wikipedia.org/wiki/Scientific_method)。

[到了17世纪，科学革命的先驱伽利略在著作《关于两种新科学的谈话》中发扬了这种科学方法，并且讨论了著名的两个小球自由落体运动的实验如何证伪古希腊博学家亚里士多德的“重的物体下落更快”的说法](https://en.wikipedia.org/wiki/Two_New_Sciences)。

经过了长期的思考与讨论，20世纪提出的假说演绎法成为了现在被广泛认可的科学方法。

### 假说演绎法

假说演绎法将科学方法的过程分解为提出问题、提出假说、预测和验证假说并分析结果。

提出问题是进行科学研究的第一步。
有时候大家可能认为问题是显而易见的。
现在我们看都知道苹果为什么会掉下来是一个问题，并且可以很容易给出答案。
但是很多人都只能意识到别人提出来的问题，只有真正进入到科学研究的过程中去，才能体会到提出一个好问题的难度和重要性。
作为研究生一年级的学生，提出一个好问题是好的研究的开始。
当问题不够好的时候，容易小而杂乱，使得自己的研究方向缺乏主线，不成体系。
所以一个深入而有价值的问题是十分重要的。

![图3：广义相对论描绘的时空坍缩](/images/2017-08-07-a-new-kind-of-science-2/spacetime_curvature.jpg)

在问题被提出之后，基于对问题的深度观察和洞见，结合自己的科学直觉，会对问题的答案有一个初步的假设。
比如牛顿看到苹果掉下来之后，给出了万有引力的假说，说万事万物（准确的说，是有质量的物体）之间都有相互吸引的力量。但是不同的科学家有不同的观察，完全可以提出不同的假说。
若干年后爱因斯坦再次审视这个问题的时候，基于自己的洞见提出了广义相对论的假说，说引力只是时空弯曲的表现，有质量的物体都会引起时空的坍缩(如图3所示)使得周围的物体向它们靠近，表现为引力。
需要注意的是科学的假说必须可以被证伪，即可以通过这个假说推论出一个可以被实验验证或推翻的结果。
从这个角度来讲，许多学科比如数学、心理学等等是否是科学还存在争议，但是在自然科学领域如物理学、化学、生物学等等，可被证伪性是被广泛认可的一个科学准则。

![图4：卡文迪许扭秤实验结构示意](/images/2017-08-07-a-new-kind-of-science-2/cavendish_experiment.png)

提出假说之后我们可以根据假说推论出许多预测，其中一些预测可以作为下一步验证假说的目标。
一个好的预测是可以将这个假说和同类假说区分开来的，并且实验上也是可行的。
牛顿提出了万有引力假说做出了很多预测，但是由于17世纪实验器械精度很差，一直没有能够有效验证。
直到18世纪卡文迪许扭秤实验(如图4所示)，通过精巧的设计器械精度很差的情况下测量了很小的引力变化，才验证了万有引力定律。

通过假说做出的预测之后需要实验来验证，一个好的验证实验必须是可重复的，并且充分控制了其他干扰因素。
当许多科学家独立验证了一个假说做出的预测之后，那么这个假说就被认为是成立的了。
但是受限于时代的因素，很可能一些之前成立的假说会被后来新的观察和实验推翻。
牛顿的万有引力定律统治了物理学很长时间，直到19世纪科学家测得在所有惯性参考系中光速都是恒定的，与万有引力定律的预测不符，大家才对其产生了质疑。
直到爱因斯坦提出了相对论，解释了万有引力定律成功解释和未成功解释的所有现象之后，这一问题才得到解决。
最近被LIGO证实的引力波也是广义相对论之前的预测之一。

这是科学方法的一般准则，也是一般科学研究基本遵守的步骤，但是要注意的是并不是所有的科学研究都会按照相同的步骤，或者在每个步骤进行到相同的程度。
科学研究还是非常需要洞察、灵感甚至一些天才的。

## 《一种新科学》是否真的是新的科学？

按照传统科学的方式，沃尔夫勒姆这种没有在前人研究的基础上进行研究，且不接受同行评议直接出书的研究过程是不科学的。
除此之外，由于《一种新科学》中的假说不可证伪，我们没有办法说明宇宙不是一个元胞自动机，所以从这个意义上来说，该假说也是不科学的。

更进一步，因为沃尔夫勒姆提出了一种新的科学，那么用现有的科学定义来评价他是不是有些不公平呢？
那么我们姑且承认这是一种新的科学，但是这又能给我们带来什么呢？
是的，这是一种全新的看待问题的视角，但同时这也意味着，对传统科学方法的彻底颠覆。
因为按照沃尔夫勒姆的理论，我们虽然知道了宇宙的本源就是元胞自动机，但是除了观测它可能发生的结果之外，并不能做出有效的预测。
因为一切预测都需要重演其整个历史，而付出了这些计算时间之后，预测也就不叫预测了。
悲观来看，我们就只能静静的看着事物的演化，却对其无能为力。
在享受着传统科学方法给我们带来的巨大的社会进步的同时，这种新的科学又何尝不是一种新的倒退呢？

另一方面，这种新的视角也是十分有趣的一种观察。
很多文学作品和影视作品都曾经设想过人类所在的宇宙只是更高等级生物的一个元胞自动机试验。
《楚门的世界》里主角楚门生来的一切都是被安排好的一个电视节目，《西部世界》里人类更是造出了与人类无异的人工智能，并将他们放于一个人造的世界里。
而最终这些影视作品里的造物都突破了自身的限制，意识到了造物主的存在并且突破了他们。
这种新的视角能否也带领人类走向突破自己的造物主的道路呢？

## 结论

沃尔夫勒姆的著作《一种新科学》让我们以全新的角度来思考宇宙的本质原理，虽然在学术上存在着种种问题，但不可否认在他比前人的工作走的更加深入，而且不失为一本很好的科普读物。
不过这种这种新的科学我认为更多的是一种新的视角，而不能代替现在的科学方法，尤其是在现在的科学方法能够极大的推动社会进步而这种新科学却让我们无能为力的时候。
所以让我们心怀着这一科学假说，继续向更深层次的知识不断的探索吧。

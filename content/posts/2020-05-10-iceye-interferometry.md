+++
title="Iceye 的干涉影像：小型 SAR 卫星的里程碑？"
date="2020-05-10"
math=true
tags = ["Iceye", "InSAR", "microsatellite"]
categories = ["随笔"]
+++


### 重磅：Iceye 突然发布干涉影像产品

在关注合成孔径雷达（SAR）和干涉合成孔径雷达（InSAR）的业界人士和研究者眼里，最近的一则重磅新闻就是芬兰的初创小雷达卫星公司 [Iceye](https://www.iceye.com) 毫无征兆地发布了[一则新闻](https://www.iceye.com/press/press-releases/sar-interferometry-demonstrated-with-an-18-day-global-repeat-by-iceye)，展示了他们的最新产品：两幅干涉图。

之所以说毫无征兆，是因为 Iceye 从 2018 年成立至今，并没有宣传过他们的 SAR 影像成品可以用来做干涉（InSAR）。对于一直关注 SAR 商业小卫星的人们来说，InSAR 是 SAR 的一个极其重要的应用分支，如果不能做干涉，那么相当于扔掉了 SAR 影像中 50% 的数据信息。所以，SAR 小卫星是否可以做干涉，一直是大家比较关注的。在 5 月之前，Iceye 似乎从来没有提起过他们的卫星有关干涉的能力或计划，而所有的宣传（Public Relations, PR）也都主要放在了变化检测（例如农业用地变化、非法船只监控）和高分辨率（[可以达到惊人的 25cm 的分辨率](https://www.iceye.com/press/press-releases/iceye-unveils-25-cm-sar-imaging-capability-with-current-sar-satellite-constellation)）上面。

{{< figure src="_image/2020-05-10-iceye-interferometry/iceye-change-detection-crops.gif" caption="Iceye 发布的农田随时间变化的 SAR 影像图。来源：[Iceye 官网](https://www.iceye.com/satellite-data#C5.1)" >}}

{{< figure src="_image/2020-05-10-iceye-interferometry/iceye-ship-detection.png" caption="Iceye 官网上所发布的用于做非法船只检测的一个互动界面。来源：[Iceye 官网](https://www.iceye.com/solutions/security/dark-vessel-detection/interactive-demo#)" >}}


而在 5 月 6 日，[Iceye 却突然在官网上发布了两张干涉图的样片](https://www.iceye.com/press/press-releases/sar-interferometry-demonstrated-with-an-18-day-global-repeat-by-iceye)。两张干涉图都是 18 天的重访周期，一张是在南非开普敦，用的是条带（stripmap） 模式，分辨率应该是 [3 m](https://www.iceye.com/sar-data/stripmap)；另外一张是在澳大利亚西北的 Point Samson，用的是聚焦（spotlight）模式，其分辨率是 [1m 左右 ](https://www.iceye.com/sar-data/spotlight)。发布的这两张图，除了说明 18 天的重访周期以外，并没有透露其它数据细节，也没有提供样例数据供大家下载。

>  Finnish New Space leader ICEYE is the first in the world to demonstrate interferometric capabilities from synthetic-aperture radar (SAR) satellites under 100kg (220 pounds) in mass. 
> 芬兰的太空商业领军公司 Iceye 是世界上第一个展示了 100 公斤以下的小卫星可以用来进行 SAR 干涉的公司。

不管怎样，对于 InSAR 研究者/从业者而言，这都是一个值得振奋的里程碑事件。正如其在官网所说，Iceye 首次实现了 100 千克以下小卫星的干涉能力。在这之前，InSAR 都是被一些更大的卫星和国家级别的研究机构所「垄断」的，例如德宇航局（DLR）和空客（ Airbus） 合资的 TerrSAR-X （1230 千克），欧空局（ESA）的哨兵一号（2200 千克！）等。以 80 千克的重量实现干涉，说明 Iceye 的相关技术已经非常先进了。

{{< figure src="/_image/2020-05-10-iceye-interferometry/iceye-insar-south-africa-kape-town.png" caption="Iceye 所发布的干涉图，地点位于南非开普敦，数据为18天重访周期的条带模式（Stripmap）。来源：[Iceye 官网](https://www.iceye.com/press/press-releases/sar-interferometry-demonstrated-with-an-18-day-global-repeat-by-iceye)" >}}

{{< figure src="/_image/2020-05-10-iceye-interferometry/iceye-insar-australia-point-samson.png" caption="Iceye 所发布的干涉图，地点位于澳大利亚的 Point Samson，数据为18天重访周期的聚焦模式（Spotlight）。来源：[Iceye 官网](https://www.iceye.com/press/press-releases/sar-interferometry-demonstrated-with-an-18-day-global-repeat-by-iceye)" >}}


### 干涉图的价值：从千里之外看毫厘之差
要解释为什么这是一个里程碑事件，就要简略地说说合成孔径雷达干涉（InSAR）。

在大部分人眼里，合成孔径雷达/雷达影像是这样的：
{{< figure src="/_image/2020-05-10-iceye-interferometry/sar-pentagon.jpg" caption="SAR 影像：五角大楼。来源：https://fas.org/irp/imint/tesar2.htm" >}}

雷达影像通常都是黑白图片，其中黑白代表了接收到的雷达信号的能量，越白代表接收到的反射雷达信号更强；越黑则是越弱。

然而，雷达的另一个重要的作用是**测距**。也就是说，雷达是可以测量物体与传感器之间的距离的。测距的精度取决于波长，精度是亚波长级别。比如 Iceye 的 X 波段是 31mm，那么理想的测距精度可以达到～1mm 左右。

是不是听起来很好？然而，天底下并没有这么好的事。因为 SAR 是用**相位** （**phase**）来记录距离的，而相位只有 0 到 360 度（一般习惯用 radian， 所以 360 度就是 $2\pi$)，到了 361 度就又回到 1 度了。这就相当于一个只有分针的钟：你只能看到现在是 16 分钟，但不知道是几点。

可是只有分针的钟并不是一无是处。比如说有人想知道两次观测隔了多久。假如 ta 第一次看到分针指在 16 分钟，然后 ta 去喝了口水，回来发现分针在 19 分钟，那么 ta 就知道时间过了 3 分钟（因为不太可能是 1 小时 3 分钟或更多……）。这就是干涉（InSAR）的意义。如果只有一张图，那么你并不知道地面物体离雷达有多远；因为你只知道距离的余（modulo）。可是如果你把两张图一比较，你就可以知道在这期间地表到传感器的距离变化有多少。因此，一张图的相位信息是没有用的；可是把两张图的相位一减，得到的干涉图就可以测量出地表的微小移动或高程信息。这就是干涉。

如果不利用相位的信息，那么就相当于雷达的数据白白扔掉了一半。因为雷达数据是用复数存储的：
$$
\mathrm{SLC}(i,j) = A(i,j) e^{-i\phi}
$$
其中 $A(i,j)$ 是 SAR 的强度图，就是我们刚刚看到的五角大楼的影像；而 $\phi$ 就是相位信息，记录着传感器到目标像素的距离的余。InSAR 利用的就是 $\phi$ 部分的信息。

{{< figure src="/_image/2020-05-10-iceye-interferometry/insar-principle.png" caption="合成孔径雷达的相位就像一个只有分钟指针的钟。来源：Q. Verburg, in QUInSAR: Temporal Parameter and Ambiguity Estimation Using Recursive Least-Squares: A Methodology for Persistent Scatterer Interferometry, Master thesis, Delft University of Technology, 2017. " >}}

### Iceye 干涉影像的质量到底如何？

虽然 Iceye 并没有提供特别多有关干涉图的有用信息，但是大家对于 Iceye 产品的干涉能力肯定还是非常的好奇。这其中大家最关心的，应该还是 Iceye 是否已经可以成熟、大规模地提供干涉产品用于商业、科研活动。如果的确如此，那么这种廉价的干涉卫星数据必将带来 InSAR 行业继欧空局哨兵数据发布之后的第二个飞跃。那么，从 Iceye 已经发布的数据出发，是否能一窥 Iceye 的 InSAR 能力呢？

#### 两张干涉图是怎么被处理的？

首先我们注意到 Iceye 的官网并没有公布两张干涉图的获取时间。从谷歌地球（ Google Earth） 上看，两个区域都比较干燥，是比较理想的做干涉实验的区域。这个也可以从两张相关性图（Coherence map）上看出来。另外，可以明显发现的是两张图都经过了滤波（Filtering），还很可能做了地理编码（Geocoding）。如果没有做 Geocoding，最后出来叠加在 Google Earth 上就不应该是正南正北，而应该有一个 10 度的倾角；当然，Iceye 也有可能只是简单裁了一下图。

至于滤波，因为官网只给出了 png 格式的图像，而且分辨率已经大大降低了，所以并不是特别好判断。开普敦的那一张干涉图，png 的分辨率只有大约 15～20 米左右；澳大利亚的那一张分辨率大约在 2.5 米左右。所以干涉图有可能还做了多视（multilook）。而究竟用的是什么滤波或者干脆就没有，就很难知道了。我比较倾向于 Iceye 做了简单的滤波，类似于高斯滤波（ Gaussian filter）之类的，而且明显可以感觉到澳大利亚的那张「磨皮」用得更狠一些，而且还把陆地上失相关的区域都「抠」掉了，给大家展示出来了比较完美的结果。

#### 从干涉图反推轨道控制

尽管似乎无法从 png 上得到太多的有用信息，还是有一点引起了我的注意，那就是开普敦那一张图上代表高程的条纹（fringe）。熟悉 InSAR 的人都知道，在有山地起伏的地方，如果忽略大气和地表沉降信号，那么干涉图上的条纹代表的是高程的变化，我们可以用条纹来反衍地表高程信息。而条纹的「密集程度」是与卫星基线（也就是两次卫星经过同一区域上空时的相对位置）相关的。从 Iceye 发布的干涉图，我们就可以反衍他们的卫星基线。

{{< figure src="/_image/2020-05-10-iceye-interferometry/height-ambiguity.png" caption="在 Google Earth 上数条纹数量并读取高程值来确定高程模糊度（height ambiguity）" >}}

为了知道一个条纹（干涉图里一轮从红到蓝，代表相位变化$2\pi$）所代表的高程，我在地图上选取了三个「小山坡」，读取了 Google Earth 上的高程值（根据我的经验，基本准确）。如下图所示，通过对几个小山坡的估计，我大概确定了一个条纹大约是高程变化 **10 米**。根据著名的公式[^height-ambiguity]：
$$
h_a = \frac{\lambda R \sin \theta}{2 B_n}
$$

[^height-ambiguity]: A. Ferretti, A. Monti Guarnieri, C. Prati, and F. Rocca, “**Equation 2.4,**” in InSAR Principles: Guidelines for SAR Interferometry Processing and Interpretation, European Space Agency, 2007. 

因为 Iceye 用的是 X 波段，所以 $\lambda=31mm$, 轨道高度是 570 km，入射角（incidence angle）在 15 到 35 度之间（参见[此处](https://www.iceye.com/hubfs/Downloadables/ICEYE-SAR-Product-Guide-2019.pdf)）。根据我们从图上所得，$h_a \approx 10m $，由此我们可以得出：
- 如果 incidence angle 为 20 度，基线为 300 米；
- 如果 incidence angle 为 30 度，基线为 440 米。

#### 三四百米的轨道控制水平如何？

在我刚刚得出这个数据的时候我是很吃惊的。因为 300～400 米的轨道控制已经算是相当出色的了。做为对比，下图是几颗「著名卫星」的基线控制。如果 Iceye 可以做到 400 米以内，那基本就可以媲美 COSMO（同样是 X 波段） 了。根据以往的经验，如果 X 波段基线可以控制到 300 米以内且保持稳定，那么无论是做高程反衍还是永久散射体时序分析（PSI），都可以达到非常好的效果。当然，取决于 Iceye 的产品策略，如果他们想卖高程产品的话，目前三四百米的基线就很不错了；如果他们想把重点放在地表沉降时序检测，则需要把轨道控制得再小一些。

不过，Iceye 如果想要卖高程数据的话，可能优势并不是很多。一个是德宇航局（DLR）的 Tandem-X 计划的高程产品已经有了，质量应该只会比 Iceye 的卫星更好；另外能做高程的传感器很多，LiDAR，photogrammetry 都可以做，高程反衍本来也并不是 InSAR 的优势所在。

{{< figure src="/_image/2020-05-10-iceye-interferometry/tsx-csk-s1-baseline.png" caption="三颗主要 SAR 卫星：德国的 TerraSAR-X、意大利的 COSMO-SkyMed 和 欧空局的 哨兵一号的基线数据对比。左边三张图即为三种卫星可以做干涉的影像基线直方图。可以看到 TerraSAR-X 基本可以控制在 200 米以内，COSMO 略差一些，500 米以上的也很多，哨兵是最好的，几乎不会超过 100 米。" >}}


### 如果 InSAR 这么好/重要，为什么现在 Iceye 才发布？

#### 技术要求

第一个重要的原因就是技术要求高。

其实传感器获取影像和照相机照相差不多。都是「摆好姿势」（传感器的姿态）然后接收信号（雷达是主动传感器，所以是发射并接收信号）。

从这点上来讲，SAR 要稍微容易一些，这就跟你去拿着相机聚焦去拍一朵小花一样，你只要端起相机「咔咔咔」对着差不多的方向拍就可以了。出来的照片里有小花的就是合格的照片。

可是，假如你现在要拍静态延时记录开花的过程，那难度就高很多了。你起码要满足以下几个方面：
1. 基本站在同一位置拍摄。如果你中间移动了，比如拿着相机去休息了一会儿，你要保证新的位置和之前的位置不会差太远，基本是在同一个点，才能和之前的对上；
2. 你的相机要对着同样的角度。也就是说，即使你在同一个位置，还要保证相机对的角度和之前几乎一样，如果差太远，新拍的照片也和前面的对不上。

现在我们回到 InSAR，以上两点对应的就是：
1. 基线（spatial baseline）。拍摄两张 SAR 影像的时间，卫星的位置必须被控制在一个范围内（通常需要在数百米内），才能做干涉；
2. 共同频谱（Common bandwidth）和 天线倾斜角度（squint angle）。这个是说天线的姿态和角度必须相同，有共同频谱，才可以做干涉。

#### 为什么小卫星更难？

我们知道，干涉最重要的就是轨道控制。卫星是通过推进器燃烧燃料来控制轨道的。如果卫星没有燃料，就会在地心引力的作用下，绕着地球做椭圆运动，但高度会慢慢降低，直到坠入大气层。

大型卫星上面所携带燃料和能源肯定更为充足。对于只有 **80 千克**的 Iceye 小卫星来说，燃料肯定是一个关键的因素。如何用极其有限的燃料来最大程度地做好轨道高度控制就成为了干涉能否成功的关键因素。另外传统大型卫星上的推进器肯定也不适用于这样的小卫星，所以如果用小型的推进器做精确的轨道控制，肯定难度也会升高。

当然，小卫星的一个优点是便宜。虽然每颗卫星的燃料少寿命短，但是因为单价低，一口气发上去 24 颗或 48 颗，就可以很好地补偿寿命短的短板。事实上，这也是这些小卫星公司的计划：通过数量众多的卫星组成一个网络，提供廉价、快速的数据服务。

### 下一步？

Iceye 是 SAR 商业小卫星的先驱者。这家位于芬兰 Espoo 的公司是从 Aalto 大学发展壮大的 「spin-off 」，用国内时髦的话说就是「科技成果转化」。从 2014 年成立至今，他们取得了非常惊人的成绩，至今已经发射了 5 颗 SAR 卫星，其中有三颗（ICEYE-X2， X4 和 X5）已经可以提供商业数据。自从 2018 年以来，Iceye 似乎有了飞跃式的发展。在技术上，这次发布干涉产品之前，他们就在 SAR 数据的质量上做出了许多提升，例如 25 厘米分辨率的数据；在资金上，他们也在 2019 年拿到了 B 轮融资，总金额达到了接近 7 千万美元。在商业上，他们也最近在波兰开设了新的办公室。在宣传上，他们的宣传力度也在 2018 年后有了明显的提升，尤其是 2019 年发射了新的卫星之后，就有更多的数据来支撑他们的宣传。在合作上，Iceye 也在紧密地和一些传统部门合作，这里面最重要的就是欧空局。例如欧空局的 SAR 软件 Snap toolbox 就在第一时支持了 Iceye 的数据，这也为 Iceye 的推广起到了良好的作用。

现在还不知道这次有关干涉数据的宣传更多的是出于从融资和满足投资人要求、亦或是 PR 的角度出发，还是 Iceye 真的已经具备了一定的 InSAR 能力，敢拍着胸脯说他们可以把 InSAR 在不久的将来投入商业化了。从这一点上，我比较赞同 [Leeds 大学的 Tim Wright 的说法](https://www.bbc.com/news/science-environment-52560809?utm_content=128725188&utm_medium=social&utm_source=twitter&hss_channel=tw-2876294235)：

>  Leeds University's Prof Tim Wright ... commented. "The possibility of doing InSAR with these microsatellites at very high resolution with rapid revisit time is really exciting and could open up many new monitoring applications (largely commercial I think)." But he added that it was now for Iceye to show it could deliver regular, quality interferograms.
> 利兹大学的 Tim Wright 教授……评论到，「能够使用这种高空间分辨率、高时间分辨率的小卫星数据做 InSAR 是非常激动人心的。这也为无数的地表监测项目打开了新的大门（尤其是商业上的）。」他接着评论到，现在是 Iceye 展示他们能够规律地提供高质量的干涉图的时候了。

无论如何，相比较于另外某个「更著名」的硅谷明星 SAR 卫星初创公司，2014 年成立至今，融资超过 8 千万，至今连自己的一颗星一景数据都没有来说，Iceye 已经非常非常优秀了。什么时候能够用上 Iceye 的干涉数据，让我们拭目以待。80 千克的 「microsatellite」 能够做出来 InSAR，这已经是一个奇迹。



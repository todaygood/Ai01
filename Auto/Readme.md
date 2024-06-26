# 智能驾驶

[论文](https://github.com/Thinklab-SJTU/Awesome-LLM4AD)

[主流自动驾驶方案的庖丁解牛](https://mp.weixin.qq.com/s?__biz=Mzg2NzUxNTU1OA==&mid=2247581823&idx=1&sn=40b4afeed8713c4849e37b4e7faea8de&chksm=ceb9adb6f9ce24a061dab87dff78de8f4943fad20cd1eec15cdea015bf7cabe8f8194d1b9819&cur_album_id=2505429071070216194&scene=189#wechat_redirect)

第一代自动驾驶系统主要模型参数量约百万级，算力需求在100TOPS量级；
第二代自动驾驶系统主要模型规模突破千万级，部分基于Transformer的模型参数量接近亿级，算力需求约200-500TOPS；
第三代自动驾驶系统由于引入大模型技术，初步估算参算量会达到百亿、千亿水平，算力需求最终则会达到2000TOPS。

[2024年自动驾驶行业，地(地平线)大(大疆)华(华为)魔(Momenta)和NV智驾会在市场形成虹吸效应吗？](https://mp.weixin.qq.com/s/aMN1pR-xD0JYllHBYESQPA)

基于自动驾驶各模块的分析总结
(1).在系统硬件架构上，多核CPU，GPU，深度学习/神经网络单元，安全冗余芯片为控制器四个必要组成部分。
(2).感知和地图：基于BEV+Transformer构建共享主干多任务感知模型，实现目标检测、运动预测、地图实时生成的重感知轻地图方案是未来2-3年内自动驾驶量产的核心框架。
(3).定位：基于消费级导航地图、定位设备，融合多传感器特征定位是降低基于高精度地图和高精度惯导成本的重要方式。
(4).规划：结合语言、知识大模型，结合端到端自动驾驶大模型和基于强化学习的反馈学习机制，构建能以自然语言方式实时描述、推理驾驶场景，能够基于驾驶目标整体优化的方案是未来重要方向。
(5).控制：基于模型预测控制，基于模型作为先验，基于实际驾驶数据的无模型强化学习控制可能是解决多场景自适应控制的方向。
(6)算法架构：含部分人为设计的中间过程，结合自然语言场景理解，基于人反馈强化学习（RLHF）大模型架构的伪端到端自动驾驶框架会是未来重要方向。




## 大模型攻入自动驾驶

[大模型攻入自动驾驶](https://m.thepaper.cn/newsDetail_forward_24961052)


自象限
财经领域创作者
2023-10-18 12:09
 

©自象限原创

作者｜罗辑

编辑｜程心

“自动驾驶的前提是安全与严谨，大模型给出'差不多'的结果是不行的。”

在今年4月初，大模型刚刚问世时，一位自动驾驶领域的资深投资人向「自象限」表达了，他对通用大模型应用在自动驾驶领域的担忧。

不被看好的原因有很多，比如大模型“胡说八道”的问题，导致大家认为它达不到自动驾驶的安全等级要求；比如大家认为大模型解决的是共性推演的问题，但自动驾驶解决的0.5%的corner case；再比如大模型要在车端落地，需要与结合前融合算法，对前端算力的要求会很高。

总而言之，通用大模型的不确定性和自动驾驶的严谨性像一个硬币的两面，落地上也面临着几座短期内难以翻越的大山。“这会是整个体系建设的问题，不是角度算法可以改变的。”这位投资人如此总结道。

尽管不被看好，但6个月过后，大模型还是以一种蛮横的方式冲进了自动驾驶行业。

打响第一枪的，仍然是特斯拉。今年8月，特斯拉端到端AI自动驾驶系统FSD Beta V12首次公开亮相，完全依靠车载摄像头和神经网络来识别道路和交通情况，并做出相应的决策。国内，自动驾驶和大模型公司都开始紧锣密鼓的布局，9月，华为盘古大模型3.0推出了自动驾驶行业大模型；10月，在毫末第九届AI Day中，也讲解了其身处自动驾驶领域对大模型的一系列探索。

从结果来看，目前大模型对自动驾驶的改变分为两个方向：一是大模型作为工具，辅助自动驾驶算法的训练，优化过程；二是大模型作为决策模型，直接驾驶车辆，改变结果。

透过国内外的探索，这条看似相悖的技术路径似乎开始一步步清晰，那么大模型究竟能给自动驾驶带来了什么？核心的技术难题又该如何解决？

大模型，更换自动驾驶训练引擎

首先，大模型正在重塑自动驾驶的训练过程。

从大模型被讨论的第一天开始，从文本到图片生成，大家就深刻意识到大模型在提高工作效率上的巨大潜力。这一点，在自动驾驶训练上也不例外。

训练自动驾驶算法，是一个漫长而庞大的工程，从数据采集、传输、管理；到数据清洗、标注、准备，到最后投入到训练自动驾驶算法的熔炉当中，中间会涉及到数十个环节。

而如今困扰自动驾驶发展的核心问题也来自于此，一个是随着绝大部分常规问题被解决，有效数据的收集难度越来越大；其次则是随着数据规模的增加，数据处理的成本也越来越高。


▲图为自动驾驶训练过程

首先是数据收集的问题。当自动驾驶走入最后0.5%的corner case阶段，场景数据在现实世界就变得可遇不可求。

为了应对这些问题，特斯拉、Waymo、Cruise等企业都在不同程度使用合成数据来模拟真实世界来训练自动驾驶。

但这种方式也存在一些弊端，比如合成数据虽然能轻松生成大量数据，提高自动驾驶训练数据的多样性。但作为人工生成的数据，合成数据并不能完全模拟真实世界的复杂和变化。过度使用合成数据，会导致自动驾驶出现“纸上谈兵”的现象，即在训练时表现很好，但一上路就不行，这种情况被称为过度拟合。

而针对这样的问题，大模型提供了一种新的解决方案。

比如使用大模型进行数据生成的技术——迁移生成。它可以基于一个真实的场景，快速生成不同时间、不同环境的情况。比如拍摄一张街道春天的照片，大模型可以快速生成这条街道雨天、刮风、下雪等不同条件、不同季节的情况。

这么做的好处在于“可控”，自动驾驶训练可以根据一些特定的需要生成一些特定的场景，而更重要的是，这些场景中包含一些真实数据，在增加训练场景丰富性的同时，又可以避免过度拟合的情况。

目前已经有厂商在逐步尝试，毫末CEO顾维灏在AI Day中便提到了该技术，清华智能产业研究院（AIR） 提出的自动驾驶模型也有类似的设置，在他们的设定中，模型会提出怎样获取不同的数据，包括真实世界数据和仿真数据。然后这些数据要经过受控管道进行清理，再经过感知和决策两大模型，最终为车辆提供决策。

其次是数据标注，数据标注并不是一次性完成的，同一张照片，不同时期，依据需要解决问题的不同，需要标注的东西也不太一样。

比如一开始需要解决的是车辆识别的问题，那么照片中重点标注的是不同的车辆，后来要解决红绿灯识别的问题，重点标注的可能就是红绿灯。总之，数据标注是一个反复，且逐步细化的过程，因此难度和成本也在持续增加。

在国外，特斯拉最早启动数据自动标注，这让原来需要几个月时间的工作可以在几周内完成。2022年6月，得益于效率的提升，特斯拉裁掉了其位于加利福尼亚圣马特奥办事处的绝大部分数据标注员工。

特斯拉之后，国内自动驾驶企业也开始跟进，将自动标注使用到日常训练中。作为特斯拉的”中国学徒“，顾维灏介绍了毫末使用大模型进行数据标注的案例。

其运用大语言模型和多模态的能力，通过将图文和文图交叉的特征做匹配的，然后再将其放到大语言模型中，针对形成于特征空间的搜索（query）特征。在这样的基础上，大模型就可以在不需要做太多准备的情况下，将之前没有标注过的，想要标注的内容标注出来。

整体上，大模型的接入优化了自动驾驶的训练过程。

如果将训练自动驾驶算法比作是金字塔的修建，那么大模型的加入，就如同将曾经依靠人力堆砌的石块，改换成现代化的起重机，加快了自动驾驶的“搭建”进程。

大模型，让自动驾驶“长出脑子”

在自动驾驶训练中，大模型就像全职助手一样不断提高算法训练的效率。但这也仅仅只是工程上的优化，大模型给自动驾驶带来的，还有更深层次改变。

这个问题要回到自动驾驶是如何进行工作的。

在大模型出现之前，自动驾驶是任务驱动的。即程序员依据一些特定的场景，编写一些解决方案的代码，当车辆在行驶过程中感知到相应的情况，便按照之前设定好方式处理。

在这个基础上，自动驾驶的发展就变成：发现一个问题，收集一些数据，然后训练一个小模型来解决这个问题，然后再发现新的问题，如此循环。

但这种模式对于问题的解决具有一定的滞后性，即问题要先被发现，然后等一段时间才能被解决。其次是泛化问题，即在同一个问题在夏天解决了并不一定在冬天解决。也正是因为如此，自动驾驶才有解决不完的corner case。

这些问题，实际指向的其实是传统自动驾驶算法“照本宣科”式的工作模式，并没有真正认识世界、理解世界，即自动驾驶并没有灵魂。

大模型的出现则为这个问题的解决给出了方向，就像大模型让虚拟人、让语音助手都长出“脑子”一样，大模型也在让自动驾驶长出“脑子”。

特斯拉的“端到端”技术又叫作“感知决策一体化”，也就是将“感知”和“决策”融合到一个模型中，直接对车下达指令，控制车辆，这样输入传感器信号后可以直接输出车控信号，大大降低了级联误差的概率，也因此大大提升了系统性能的上限，整体潜力极大。


▲ 图源马斯克Twitter

目前国内还未能做到真正的“端到端”，比如毫末DriveGPT仍然分为感知大模型和认知大模型两部分。

感知大模型除了要根据车端输入的信号做三维重建，还要加上时序特征形成一个四维空间。在此基础上，毫末引入多模态大模型，多模态大模型已经做了许多文本和对齐的工作，这个时候再和4D语义空间做对齐，就可以把自动驾驶传感器看到的这些东西全部语义化，这样就形成了通用的，识别万物的能力。

而有了这样的能力之后，结合认知大模型就可以结合驾驶时的信息和行驶目标，比如直行、变道、左转等信息，给出相应的驾驶决策和驾驶解释，然后大模型将其转化为自动驾驶的语言，通过Drive Prompt和自动驾驶系统做交互。

本质上，大模型就像是自动驾驶的“领航员”和“翻译官”，它理解驾驶的目标和意图，它识别和感知环境，然后做出决策并将其翻译成自动驾驶的语言，向自动驾驶系统下达合适的指令。

当然，从人的角度来讲，驾驶车辆的过程需要的除了识别万物，还有对环境中所有物体运动方向的预判，这样才能在面对复杂交通环境时提前做出反应。

大模型同样对自动驾驶带来了这方面的改进。

2022年，特斯拉在年底的AI Day上就曾提出过一个名叫交互搜索（Interaction Search）的规划模型，其主要由树搜索，神经网络轨迹规划和轨迹打分三部分组成，可以有效预测道路交通参与主体的行为轨迹。

从这可以看到，自动驾驶的决策已经从之前，依靠单一信息进行分布决策，变成了多种信息汇总之后的统一决策。


▲ 自动驾驶的决策路径

即大模型的决策越来越像是一个整体。

目前生成未来世界这项技术可以根据当前的视频、图片，生成未来2~5秒的情况，其预测2s后准确率达到85%，这可以让AI对未来有一些预判。同时，预测未来的技术也可以用在自动驾驶训练上，比如可以生成未来的图片，然后基于真实图片和生成的未来的图片再进行自监督学习，以此来提升整个视觉大模型识别的判断的能力。

它让自动驾驶越来越成为一个“整体”，正如清华大学智能产业研究院院长张亚勤说的那样，“AI 大模型带来了从判别式 AI 到生成式 AI 的新技术范式变革，自动驾驶达到最后的安全、可靠阶段一定是端到端方式实现。”

自动驾驶的底层进化

成为“整体”，自动驾驶中关于这个的讨论其实并不是在大模型热度起来之后才开始的。

2022年，当关于自动驾驶的讨论还聚焦在芯片和电子电气架构的时候，全球著名的汽车零部件供应商博世曾提出，汽车电子电气架构将从分布式向域集中式和中央计算过渡。

早期的汽车电子电气架构是以ECU（Electronic Control Unit 电子控制单元）为主，一辆汽车通常有30到100个ECU不等，分别控制汽车的引擎、变速器、制动等等功能。随着汽车智能化的进程，相关功能的ECU逐渐被整合成域控制器，目前智能汽车通常有动力域、底盘域、车身域、座舱域和自动驾驶域五个。

在这个基础上，智能汽车的电气架构还在向一个“整体”演变，最终将会形成由一个统一中央计算单元控制的形式。2016年，特斯拉发布的Model 3实现了中央域控制架构的雏形，当时被行业认为在电子电气架构方面领先传统车企6年以上。

从“散装”到“整体”，这是智能汽车硬件层面的变化，这种变化也推动着自动驾驶软件层面向一个“整体”发展，而契机就是大模型。

关于自动驾驶与大模型，张亚勤提到，“自动驾驶不是一个模型，而是多个模型的组合。”这其实正好对应智能汽车硬件域控制器的发展阶段。

这也是华为盘古大模型3.0的思路，华为云EI服务产品部部长尤鹏认为，通过数智融合架构打破数据、AI资源管理边界，在一个平台即可完成开发、测试、交付上线工作，让业务创新提效2倍，实现数据加速；借助盘古大模型在认知、感知、决策、优化等全领域的能力，车企可以快速基于盘古训练出自己需要的模型，实现算法加速；同时，华为还提供底层昇腾算力平台，解决自动驾驶对算力的高需求，做到千卡训练数月不中断，打通“全链路”，实现算力加速。

“全链路的模型化是3.0时代的一个重要的演进思路，最终演变成端到端的大模型。”顾维灏说。

而一旦完成了全链路的打通，这样的改变带来的将是大范围且高速迭代。正是因为“端到端”技术，马斯克曾放出豪言“将可能在今年年底实现完全的自动驾驶”。这句话虽然不排除马斯克吹牛的成分，但我们也可以从中看出“端到端”技术的巨大潜力。

总的而言，对于自动驾驶来说，大模型并不是一种决策方式，也不单单是指一种技术，而更应该是自动驾驶发展的一种最终形态。

当然，虽然大模型给自动驾驶的落地带来了巨大的想象力，但实际的应用和落地过程仍然面临许多问题。

比如最直接的问题就是如何将云端大模型的能力应用到车端。

目前行业普遍应用的方式有三种：

第一种是将大模型蒸馏到小模型，应用到车端。这具体又分为两种路线，一种是通过大模型给数据打标签，监督小模型学习；另一种是将大模型上的Feature map 和小模型上的Feature map进行对齐，然后来完成小模型能力的提升。

从毫末公布的工作效率来看，一个模型的蒸馏需要好几个月，但能够帮助自动驾驶车端模型在个别任务上的感知指标提升5%。

第二种是在云端通过大模型构建一种能力，然后再通过减脂、蒸馏等方式将大模型的能力蒸馏到车端的小模型上，来完成车端小模型的进步。

第三种则是直接使用云端大模型。毕竟虽然云端传输会面临信号、安全、延迟等问题的困扰，但也并不意味着所有决策都需要在车端完成。云端大模型具有更强的泛化能力和解释能力，对于任务实时性和网络信号较好的地方，也存在可能让车端的一些通信和云端大模型进行交流，然后让云端大模型完成车端工作的情况。

除了从将大模型运用到车端之外，大模型指导的自动驾驶还有许多人类生活的常识需要学习。比如路沿的方向是不是能走，面临多个路口的时候各个方向是不是一定按照车道线走，这些在实际交通实践中约定俗成的东西大模型还无法掌握。

“现在解决这些问题就需要加许多约束，而一旦加约束，这个系统就变得不聪明了。”顾维灏提出了其中的逻辑悖论。

## haomo.ai  毫末智行， 中国量产自动驾驶第一名

https://www.haomo.ai/mana

[毫末智行 自动驾驶 生成式大模型, DriveGPT ](https://drivegpt.haomoai.com/)


## waymo

[Waymo最新最强自动驾驶模拟器，刚刚对外开源了](https://36kr.com/p/2482327176025988)

Waymo联手谷歌，发布最新自动驾驶仿真模拟器。

## 清华DriveVLM

[DriveVLM](https://tsinghua-mars-lab.github.io/DriveVLM/)


## 小马智行 poly.ai

彭军
联合创始人兼首席执行官
作为自动驾驶行业的领导者，彭军博士秉承“以事聚人，因人成事”的思想汇集最优秀的人、解决最难的事，以实现未来出行方式的彻底革新。在彭博士的带领下，小马智行已迅速成长为行业领导者之一。创立小马智行之前，彭博士曾担任百度自动驾驶部门首席架构师，负责百度自动驾驶的整体战略规划与技术发展。他拥有斯坦福大学博士学位以及清华大学学士学位。

楼天城
联合创始人兼首席技术官
楼天城博士是全球闻名的计算机编程大牛，以比赛 ID “ACRush” 为计算机编程界所知。他连续11年蝉联TopCoder中国区冠军，并且两次获得谷歌全球编程挑战赛冠军。楼博士投身于自动驾驶领域，坚信技术将为人们创造更安全更高效的出行未来。创立小马智行之前，楼博士是百度历史上最年轻的T10工程师。他的职业生涯开始于谷歌，曾在Google X（Waymo）从事无人车技术开发。他拥有清华大学博士及学士学位。

## 北京初速度 MomentQ

https://www.momenta.cn/technology.html

 MSD（Momenta Self-Driving），是Momenta 完全无人驾驶解决方案，广泛应用于出租车和私家车等场景。 MSD 采用了一套极具行业竞争优势的技术路径 - “飞轮式L4“，有效解决完全无人驾驶的长尾问题… 

 Mpilot是针对私家车前装可量产的高度自动驾驶全栈式解决方案，主要的核心产品包括Mpilot X 等端到端的全场景，连续的高度自动驾驶解决方案，覆盖高速/城市快速路、泊车和城区等场景… 
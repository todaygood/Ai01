# pyTorch

https://zh.wikipedia.org/wiki/PyTorch

PyTorch是一个开源的Python机器学习库，基于Torch库[2][3][4]，底层由C++实现，应用于人工智能领域，如计算机视觉和自然语言处理[5]。它最初由Meta Platforms的人工智能研究团队开发，现在属于Linux基金会的一部分[6][7][8]。它是在修改后的BSD许可证下发布的自由及开放源代码软件。 尽管Python接口更加完善并且是开发的主要重点，但 PyTorch 也有C++接口[9]。

许多深度学习软件都是基于 PyTorch 构建的，包括特斯拉自动驾驶[10]、Uber的Pyro[11]、Hugging Face的Transformers[12]、 PyTorch Lightning[13][14]、和Catalyst[15][16]。

概述
PyTorch主要有两大特征：[17]

类似于NumPy的张量计算，可使用GPU加速；
基于带自动微分系统[18][19]的深度神经网络[20]。
PyTorch包括torch.autograd、torch.nn、torch.optim等子模块[20]。

PyTorch张量
PyTorch定义了一个名为张量(Tensor (torch.Tensor)) 的类别来存储和操作同构多维矩形数字数组。 PyTorch张量与NumPy数组类似，但也可以在支持 CUDA 的 英伟达 GPU 上运作。 PyTorch 也一直在开发对其他 GPU 平台的支持，例如 AMD 的 ROCm 和 Apple 的Metal Framework[21]。

PyTorch 支持各种张量子类型[22]。

PyTorch神经网络
PyTorch定义了一个名为 nn (torch.nn) 的类来描述神经网络并支持训练。



## 标量、矢量、向量、张量

标量是0阶张量，向量是一阶张量，张量是张量（废话）。

理解了张量的“阶”的概念，那么就明白了三者之间的关系了。

简单来说： 标量表示值， 矢量表示位置， 张量表示整个空间。

以二维空间中的矢量含义为例来解释，按照矢量的方向(与X轴的夹角)，移动矢量大小（长度）的距离，就确定了一个点（位置）。这当中移动距离即矢量大小是标量，整个二维平面空间是张量


张量是一种表示物理量的方式，这个方式就是用基向量与分量组合表示物理量（Combination
of basis vector and component）。由于基向量可以有丰富的组合，张量可以表示非常丰富的物理量。此外，张量所描述的物理量是不随观察者或者说参考系而变化的，当参考系变化时（其实就是基向量变化），其分量也会相应变化，最后结果就是基向量与分量的组合（也就是张量）保持不变。考虑到张量有如此强大的表示能力，又不随观察者不同而变化，能够有效的表示宇宙间的万物，Lillian
R. Lieber给了张量一个形象的称呼the fact of the
universe.

作者：White Pillow
链接：https://www.zhihu.com/question/23720923/answer/32739132
来源：知乎
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。


如果一个物理量，在物体的某个位置上只是一个单值，那么就是普通的标量，比如密度。如果它在同一个位置、从不同的方向上看，有不同的值，而且这个数恰好可以用矩阵乘观察方向来算出来，就是张量，比如物体的内应力、转动惯量。


挖个坟吧。

比如手持棍子的一端。

标量就是知道棍子的长度，但是你不会知道棍子指向哪儿。

向量就是不但知道棍子的长度，还知道棍子指向前面还是后面。

张量就是不但知道棍子的长度，也知道棍子指向前面还是后面，还能知道这棍子又向上/下和左/右偏转了多少。


## TPU 

Tensor Programming Unit， TPU
TPU 比 GPU 快，现在广泛使用和可用。PyTorch 不像处理 TPU 一样精通，但可以使用 XLA 等第三方插件解决此问题。


## PyTorch 的工作原理

[nvidia pyTorch](https://www.nvidia.cn/glossary/data-science/pytorch/)


PyTorch 和 TensorFlow 的相似之处在于，两者的核心组件都是张量和图形。

- 张量
张量是一种核心 PyTorch 数据类型，类似于多维数组，用于存储和操作模型的输入和输出以及模型的参数。张量与 NumPy 的 ndarray 类似，只是张量可以在 GPU 上运行以加速计算。

- 图形  
神经网络将一系列嵌套函数应用于输入参数，以转换输入数据。深度学习的目标是通过计算相对损失指标的偏导数（梯度），优化这些参数（包括权重和偏差，在 PyTorch 中以张量的形式存储）。在前向传播中，神经网络接受输入参数，并向下一层的节点输出置信度分数，直至到达输出层，在该层计算分数误差。在一个称为梯度下降的过程中，通过反向传播，误差会再次通过网络发送回来，并调整权重，从而改进模型。

图形是由已连接节点（称为顶点）和边缘组成的数据结构。每个现代深度学习框架都基于图形的概念，其中神经网络表示为计算的图形结构。PyTorch 在由函数对象组成的有向无环图 (DAG) 中保存张量和执行操作的记录。在以下 DAG 中，叶是输入张量，根是输出张量。


## todo 

https://pytorch.org/get-started/locally/

https://github.com/INTERMT/Awesome-PyTorch-Chinese



## EXECUTORCH

ExecuTorch 地址：https://github.com/pytorch/executorch

学习文档：https://pytorch.org/executorch/stable/index.html

随着 ExecuTorch 的开源，预示着 AI 应用程序在设备上本地运行、而需连接到服务器或云成为可能。我们可以将 ExecuTorch 理解成一个 PyTorch 平台，其能提供基础设施来运行 PyTorch 程序，从 AR/VR 可穿戴设备到标准的 iOS 和 Android 设备的移动部署。

ExecuTorch 最大优势是可移植性，能够在移动和嵌入式设备上运行。不仅如此，ExecuTorch 还可以提高开发人员的工作效率。

据了解，Meta 已经验证了这项技术，并将其用于最新一代的雷朋智能眼镜，而这款眼镜也是 Meta 最近发布的 Quest 3 VR 头显的一部分。Meta 表示，作为开源 PyTorch 项目的一部分，他们旨在进一步推动该技术的研究，从而迈入在设备上实现 AI 推理的新时代。


## PyTorch模型开发模板：关键概念与实践

https://developer.baidu.com/article/details/1591168

随着人工智能和机器学习的飞速发展，PyTorch作为一种流行的深度学习框架，已经在模型开发和应用领域取得了显著成果。本文将重点介绍PyTorch模型开发模板的关键概念与实践，旨在帮助读者更好地理解和应用PyTorch。


首先，让我们对PyTorch模型进行简要定义。在计算机科学中，PyTorch模型是一系列参数和算法的集合，用于在大量数据中寻找潜在模式和关系。这些模型在训练过程中通过不断调整参数以最小化预定义损失函数，从而不断提高模型的预测能力和泛化性能。

为了更好地开发PyTorch模型，我们需要先搭建合适的开发环境。首先，

从硬件配置上讲，开发PyTorch模型需要具备一定的计算资源，包括高性能CPU、GPU等。此外，为方便模型训练和调试，内存大小也应给予充分保障。

在软件环境方面，我们需要安装Python解释器以及PyTorch库本身。注意，根据您的操作系统和硬件配置选择合适的安装版本，并确保与其他依赖库兼容。


接下来，我们将详细介绍PyTorch模型的开发流程。

首先是模型设计，根据实际问题和数据特征，选择合适的网络架构和算法。例如，对于图像分类问题，您可以选择使用ResNet、VGG等经典网络结构。然后是模型仿真，通过在部分数据集上训练模型并测试其性能，调整模型结构和参数以优化性能。最后是代码编写，将模型设计和仿真结果转化为Python代码，便于后续模型部署和应用。


在PyTorch模型开发过程中，我们可能遇到一些常见问题。例如，模型参数选择问题，如果参数设置不当，可能会导致模型训练困难或性能不佳。解决方法包括尝试不同的参数组合，参考领域知识和经验，或使用自动化调参工具等。另外，代码调试也是开发过程中必不可少的一部分。我们可以通过打印关键变量、添加断点等方式来检查代码运行过程中出现的问题，确保代码的正确性和稳定性。


总之，PyTorch模型开发模板的价值在于提高开发效率、降低应用难度。通过深入了解PyTorch模型的关键概念与实践，我们可以更好地应用这一框架解决实际问题同时不断提升模型的性能和应用范围。因此，掌握PyTorch模型开发模板的关键概念与实践技能对人工智能和机器学习领域的从业者来说显得尤为重要。
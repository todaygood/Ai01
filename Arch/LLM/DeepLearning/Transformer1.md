# Transformer

Transformer是一种深度学习基础模型，可以理解为一种算法，而Pytorch是一种深度学习框架，不是具体的算法，是用来搭建算法的，可以理解为是一种脚手架。
所以Transformer和Pytorch没有必然联系，Transformer可以用Pytorch来实线，也可以用别的深度学习框架(例如Tensorflow)来实现。

作者：小满哥
链接：https://www.zhihu.com/question/620790653/answer/3251437688
来源：知乎
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

[信我！保准能看懂！深入浅出+通俗理解Transformer及其Pytorch源码！！！！](https://mp.weixin.qq.com/s/d5hbBjizOrlLSj-O9jOTZA)

https://juejin.cn/post/7330971486226858021

##  Transformer模型

Transformer模型是一种基于注意力机制（Attention Mechanism）的深度学习模型，广泛应用于自然语言处理领域。Transformer模型的核心思想是通过计算各个词与其他词之间的注意力权重，从而获得句子级别的表示。Transformer模型的具体算法如下：

输入序列X={x1, x2, ..., xn}，首先通过嵌入层转换为词向量；
计算每个词与其他词之间的注意力权重，得到Query、Key、Value三个矩阵；
计算Self-Attention矩阵，得到注意力权重的矩阵A；
对Self-Attention矩阵进行归一化处理，得到 normalized Self-Attention矩阵An；
计算输出Y={y1, y2, ..., yn}，通过输入序列X与normalized Self-Attention矩阵An按元素乘积，然后加上偏置项；
对输出Y进行线性变换，得到最终的输出O。

Transformer模型的数学表达式如下：
Q=Wq⋅X+bqK=Wk⋅X+bkV=Wv⋅X+bvA=softmax(Q⋅KTdk)An=A∑AO=An⋅V+boQ = W_q \cdot X + b_q \\
K = W_k \cdot X + b_k \\
V = W_v \cdot X + b_v \\
A = softmax(\frac{Q \cdot K^T}{\sqrt{d_k}}) \\
An = \frac{A}{\sum A} \\
O = An \cdot V + b_oQ=Wq​⋅X+bq​K=Wk​⋅X+bk​V=Wv​⋅X+bv​A=softmax(dk​​Q⋅KT​)An=∑AA​O=An⋅V+bo​
其中Wq、Wk、Wv是权重矩阵，bq、bk、bv是偏置项，dk是隐藏单元的维度，softmax是Softmax函数。

### ResNet模型

ResNet模型是一种深度残差网络，广泛应用于计算机视觉领域。ResNet模型的核心思想是通过引入残差块，克服深度网络训练难度的问题。ResNet模型的具体算法如下：

输入图像X，经过Conv2D、BatchNormalization和ReLU激活函数处理；
输入X经过几个残差块，每个残差块包含几个Conv2D、BatchNormalization和ReLU激活函数；
输出Y=F(X)+X，其中F(X)是残差块的输出。

ResNet模型的数学表达式如下：
Y=F(X)+XY = F(X) + XY=F(X)+X
其中F(X)是残差块的输出。

作者：OpenChat
链接：https://juejin.cn/post/7330971486226858021
 
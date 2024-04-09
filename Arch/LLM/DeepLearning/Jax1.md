# JAX 

[Github1.3万星，迅猛发展的JAX对比TensorFlow、PyTorch](https://cloud.tencent.com/developer/article/2251508)


JAX 是来自 Google 的一个相对较新的机器学习库。它更像是一个 autograd 库，可以区分原生的 python 和 NumPy 代码。JAX 的一些特性主要包括：

正如官方网站所描述的那样，JAX 能够执行 Python+NumPy 程序的可组合转换：向量化、JIT 到 GPU/TPU 等等；
与 PyTorch 相比，JAX 最重要的方面是如何计算梯度。在 Torch 中，图是在前向传递期间创建的，梯度在后向传递期间计算， 另一方面，在 JAX 中，计算表示为函数。在函数上使用 grad() 返回一个梯度函数，该函数直接计算给定输入的函数梯度；
JAX 是一个 autograd 工具，不建议单独使用。有各种基于 JAX 的机器学习库，其中值得注意的是 ObJax、Flax 和 Elegy。由于它们都使用相同的核心并且接口只是 JAX 库的 wrapper，因此可以将它们放在同一个 bracket 下；
Flax 最初是在 PyTorch 生态系统下开发的，更注重使用的灵活性。另一方面，Elegy 受 Keras 启发。ObJAX 主要是为以研究为导向的目的而设计的，它更注重简单性和可理解性。 


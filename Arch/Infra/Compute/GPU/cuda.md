# CUDA

3. CUDA 简介
CUDA (Compute Unified Device Architecture)，通用并行计算架构，是一种运算平台。CUDA 由 NVIDIA 公司在 2007 年发布，⽆需图形学API，采⽤类C语⾔，开发简单。

CUDA 是一种专⽤异构编程模型，CUDA是基于C语⾔的扩展，例如扩展了⼀些限定符 device、shared等，从3.0开始也⽀持 C++ 编程。

基于 CUDA 开发的程序代码在实际执⾏中分为两种：

运⾏在CPU上的宿主代码（Host Code）
运⾏在GPU上的设备代码（Device Code）
运⾏在 GPU 上的 CUDA 并⾏计算函数称为 kernel函数（内核函数），⼀个完整的 CUDA 程序是由⼀系列的设备端 kernel 函数并⾏部分和主机端的串⾏处理部分共同组成的。

kernel 在GPU上以多个线程的⽅式被执⾏，我们学的 CUDA 编程主要就是学怎么写 kernel 函数
————————————————

                            版权声明：本文为博主原创文章，遵循 CC 4.0 BY-SA 版权协议，转载请附上原文出处链接和本声明。
                        
原文链接：https://blog.csdn.net/qq_43799400/article/details/131216479


## cuda installation

https://github.com/NVIDIA/cuda-samples/

https://docs.nvidia.com/cuda/cuda-installation-guide-linux/





### python pdm 和miniconda 

https://zhuanlan.zhihu.com/p/554965293


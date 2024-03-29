# 英伟达 GPU

型号有V100 有些老， A100,H100->A800, H800 ->H20, L20, L2 ，降级的H20 和国产GPU性能差不多。

由于AI训练、推理重度依赖芯片的浮点算力，尤其是半精度浮点算力（上一篇文章中有所介绍，点我回顾），这里对浮点算力的度量单位做一个简单介绍：

FLOP：Floating Point Operations Per Second，浮点操作/秒
TFLOPS：teraFLOPS，一万亿次浮点运算/秒
PFLOPS：petaFLOPS，一千万亿次浮点运算/秒，1PFLOPS=1000TFLOPS
EFLOPS：exaFLOPS），一百亿亿次浮点运算/秒，1EFLOPS=1000PFLOPS

## NCCL

https://docs.nvidia.com/deeplearning/nccl/user-guide/docs/overview.html

The NVIDIA Collective Communications Library (NCCL, pronounced “Nickel”) is a library providing inter-GPU communication primitives that are topology-aware and can be easily integrated into applications.

NCCL implements both collective communication and point-to-point send/receive primitives. It is not a full-blown parallel programming framework; rather, it is a library focused on accelerating inter-GPU communication.


## MSCCL

https://www.ngdcn.com/post/278.html

MSCCL 是一个建立在NCCL之上的加速器间通信框架，并使用其构建块来执行自定义编写的集合通信算法。MSCCL 的愿景是提供一个统一、高效和可扩展的框架，用于跨多个加速器执行集合通信算法。为实现这一目标，MSCCL 具有多种功能：

◼ 可编程性：加速器之间的互连具有不同的延迟和带宽。因此，通用的集合通信算法不一定适用于所有拓扑和缓冲区大小。MSCCL 允许用户为给定的拓扑结构和缓冲区大小编写超优化的集合通信算法。这可以通过两个主要组件实现：MSCCL toolkit和MSCCL runtime（此 repo）。MSCCL toolkit包含一个高级 DSL (MSCCLang) 和一个为 MSCCL 运行时（此 repo）生成 IR 以在后端运行的编译器。MSCCL 将始终在没有自定义算法的情况下，MSCCL 将自动回退到 NCCL 的通用算法。例子提供了有关 MSCCL toolkit与运行时如何工作的一些实例。有关更多信息，请参阅MSCCL toolkit.

◼ Profiling/分析：MSCCL 有一个分析工具NPKit，它为每个原始发送和接收操作提供详细的时间线，以了解给定集合通信算法中的瓶颈。

## TCCL 

[TCCL简介](https://cloud.tencent.com/document/product/1646/93319) 

## ACCL 

ACCL（Alibaba Collective Communication Library）是一款高性能通信库，提供了AllReduce、 AllToAllV、Broadcast等常用集合操作接口以及点到点Send/Recv接口，为多机多卡训练提供高效的通信支持。本文为您介绍如何安装ACCL库。

背景信息
ACCL面向阿里云灵骏架构设计，通过算法与拓扑的深入协同来收获更好的通信性能，充分挖掘高性能RoCE网络的带宽效率，最大化分布式训练系统的可扩展性。

ACCL提供了简单易用的C++ API，语义与MPI等主流集合操作接口相近。ACCL提供了对PyTorch、Horovod 等深度学习框架以及数据并行、模型并行等主流并行训练模式的支持，便于深度学习用户快速使用。

ACCL的关键特性包括：

异构拓扑感知，例如节点内PCIE与NVLink/NVSwitch、节点间多轨RDMA网络，分层混合算法设计，充分利用不同互连的带宽。

端网协同选路，算法与拓扑协同设计实现无拥塞通信，支撑训练性能上规模可扩展。

端侧RoCE LAG感知、在网多流负载均衡，多任务并发、资源争抢时保障整体吞吐。

https://help.aliyun.com/zh/pai/user-guide/installation-1



## A100，H100

todo 待学习 

[【GPU】完整的软件栈](https://mp.weixin.qq.com/s/W7wFK9S0pnEBs7a7TKMTyQ),内容来自：bilibili-龚大的杂货铺的学习笔记

https://www.nvidia.com/en-eu/data-center/h100/

https://www.nvidia.com/en-eu/data-center/technologies/hopper-architecture/


## GPU in k8s 

https://github.com/stackhpc/kube-perftest

https://github.com/NVIDIA/k8s-device-plugin

https://github.com/Mellanox/network-operator

https://github.com/NVIDIA/kubevirt-gpu-device-plugin


### NVlink  vs HCCS 

todo 待学习
https://www.nvidia.com/en-eu/data-center/nvlink/





###  CUDA vs CANN 

编程框架 

[247.2k star! 超强大的私有化ChatGPT，支持图像识别/文生图/语音输入/文本朗读，个人电脑可运行](https://mp.weixin.qq.com/s/ZzYc7hF68rRYa5tfh4y3mg)

[英伟达GTC大会——与AI基础设施及中国相关的主题](https://mp.weixin.qq.com/s/tUz3bA-i0FFL1fFIaq_Kcw)

[Nvidia芯片路线图解析：机遇与风险](https://mp.weixin.qq.com/s/oXluH6kXkV75DNPhkrg-tQ)

[HPC与AI：完美融合](https://mp.weixin.qq.com/s/UNJoLibSnk_ReOBLFHN0JQ)

[AI基础设施规划：新的路径](https://mp.weixin.qq.com/s/T7FjobpVEFHBhZEFRxBowA)
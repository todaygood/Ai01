# Tencent RDMA

[腾讯星脉网络](https://mp.weixin.qq.com/s/47vTvx0pH40WDh1QJFd80A)

星脉网络主要特点有：采用无阻塞 Fat-Tree 拓扑，单集群规模支持 2K GPU，超 EFLOPS（FP16）的集群算力；可灵活扩展网络规模，最大支持 32K GPU 计算集群；计算网络平面配备 8 张 RoCE 网卡，提供 1.6Tbps 的超高带宽接入。


## TCCL 

[TCCL简介](https://cloud.tencent.com/document/product/1646/93319)  

TCCL（Tencent Collective Communication Library）是一款针对腾讯云星脉网络架构的高性能定制加速通信库。主要功能是依托星脉网络硬件架构，为 AI 大模型训练提供更高效的网络通信性能，同时具备网络故障快速感知与自愈的智能运维能力。TCCL 基于开源的 NCCL 代码做了扩展优化，完全兼容 NCCL 的功能与使用方法。TCCL 目前支持主要特性包括：
双网口动态聚合优化，发挥 bonding 设备的性能极限。
全局 Hash 路由（Global Hash Routing），负载均衡，避免拥塞。
拓扑亲和性流量调度，最小化流量绕行。
操作场景

本文介绍如何在腾讯云环境中配置 TCCL 加速通信库，实现您在腾讯云RDMA环境中多机多卡通信的性能提升。在大模型训练场景，对比开源的 NCCL 方案，TCCL 预计约可以提升 50% 带宽利用率。


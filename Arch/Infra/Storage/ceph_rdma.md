# rdma on ceph 

[XSKY开源InfiniBand RDMA互联支持 加速Ceph能效再创新高](https://searchstorage.techtarget.com.cn/6-15321/)

RDMA（Remote Direct Memory Access）是通过利用硬件 Offload 能力，解决网络传输中的延迟，提供吞吐的技术。在高性能计算领域中， RDMA 被大量使用于网络数据传输与运算交互。

RDMA 定义了一种异步网络编程接口，称做 RDMA Verbs。应用程序主要于 Verbs 交互实现 RDMA 的优势。Verbs 掩盖了底层硬件差异，因此，无论 InfiniBand 还是以太网都可作为 Verbs 的后端，于是可实现RoCE（RDMA over Converged Ethernet）。

xsky2

在 RDMA 的世界里，主要有几种协议簇。第一是 RDMA 之下的协议栈，如iWARP，RoCE，Infiniband HCA，RoCE v2 甚至 Software RoCE。这些主要是为RDMA提供底下的传输真实介质和链路实现。第二种是RDMA之上的应用协议，在存储领域包括iSER（iSCSI over RDMA），SMB 3 with SMB Direct，NFS/RDMA，SRP（SCSI over RDMA），以及现在最火热的NVMe over Fabric。

Host Network现在于NVMe Over Fabric的领域最为火热，如下图所示，Head Node Cluster Network和Storage Network 实际上作为传统存储机头的交换网络以及机头跟存储介质池的网络。前者过去通常是PCIe或者InfiniBand，后者通常是SAS或者Infiniband。在Ceph中，这两个也对应了 Ceph 的 Public Network 和 Cluster Network。

而在目前主流分布式软件定义存储里，仅华为公司的 FusionStorage 对外公开支持 InfiniBand/RDMA。而 Ceph 过去的 Infiniband/RDMA 虽然在社区被提及过，实际上是概念验证阶段，最大的原因也许是 Ceph 的网络接口以及规定语意比较复杂，使得在2014 年就已经进入主线的 XioMessenger（基于 AccelIO）至今未能满足Ceph核心对于网络层状态的需求而被投入应用。



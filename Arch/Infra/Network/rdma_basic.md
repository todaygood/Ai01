# RDMA 

[RDMA tutorial](https://github.com/StarryVae/RDMA-tutorial/blob/master/tutorial.md)
[RDMA杂谈](https://www.zhihu.com/column/c_1231181516811390976)
[【RDMA】RDMA 学习资料总目录](https://blog.csdn.net/bandaoyu/article/details/120485737)
[【RDMA】技术详解（四）：RDMA之Verbs和编程步骤](https://blog.csdn.net/bandaoyu/article/details/112860396)

RDMA的一条连接称为 一个QP(queue pair),总共有三种连接类型，分别是RC,UD,UC

RC: reliable connection 可靠链接
MR：memory region 内存区域， 一块内存区域是一块受RDMA管理的连续内存

PD： protection domain,保护域，用于做RDMA相关的资源隔离，QP和MR等资源必须隶属于某一个保护域；
RQ： Receive Queue, 接收队列
SQ： Send Queue， 发送队列
RR： Receive Request,
SR:  Send Request, 
RR和SR 统称为WR, 

CQ： Completion Queue ,用于存放完成事件；
CQE: Completion Queue Entry , 当一个RR或者SR被网卡执行后生成一个完成事件，并放入CQ; 

[RDMA入门介绍](https://zhuanlan.zhihu.com/p/652925814)


RDMA verbs API完全不同于socket API，因为verbs数据接口是真正的异步非阻塞的，理解了这句话也就理解了verbs编程的要义。上面一堆的概念都是围绕异步非阻塞通信展开的。

完整的通信过程可描述为：通信双方先建立qp，接收的一方需要通过qp将接收请求RR放入接收队列RQ，发送的一方需要通过qp将发送请求SR放入发送队列SQ，然后网卡开始去做真正的数据收发（注意数据收发过程无需任何CPU参与）。当数据收发完成后，网卡会在完成队列CQ中产生对应的完成事件通知应用层。同时为了保证数据通路的效率，RDMA操作内存必须是经过内存注册的。



ROCE 协议依赖于无损网络，对丢包极其敏感，通常需要使用交换机的PFC功能来实现无损网络

iWarp协议利用TCP充当RDMA的传输层。 

RoCE集群一般不会超过1千台。 

PFC风暴
PFC死锁







## eRDMA

ERDMA enables large-scale RDMA acceleration capability in Alibaba ECS
environment, initially offered in g7re instance. It can improve the
efficiency of large-scale distributed computing and communication
significantly and expand dynamically with the cluster scale of Alibaba
Cloud.

ERDMA is a RDMA networking adapter based on the Alibaba MOC hardware. It
works in the VPC network environment (overlay network), and uses iWarp
transport protocol. ERDMA supports reliable connection (RC). ERDMA also
supports both kernel space and user space verbs. Now we have already
supported HPC/AI applications with libfabric, NoF and some other internal
verbs libraries, such as xrdma, epsl, etc,.

For the ECS instance with RDMA enabled, our MOC hardware generates two
kinds of PCI devices: one for ERDMA, and one for the original net device
(virtio-net). They are separated PCI devices. The link operation is
handled in erdma driver after the device probe successfully.

https://lwn.net/Articles/895664/

https://github.com/alibaba/elastic-rdma-drivers

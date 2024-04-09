# RDMA in NFS

## nfs using RDMA 

https://docs.oracle.com/cd/E19253-01/819-7059/rfsrefer-fig-155/index.html

如果 RDMA 传输在客户机和服务器上都不可用，则 TCP 传输为首选备用传输协议，
如果 TCP 不可用，则会再使用 UDP。但是请注意，如果使用 proto=rdma 挂载选项，则会强制 NFS 挂载仅使用 RDMA。

RoCE v2
RoCE 版本 2 协议在 IPv4 或 IPv6 协议的 UDP 上存在。对于 RoCE v2，UDP 目标端口号为 4791。
RDMA_CM 设置客户端和服务器之间用来传输数据的可靠连接。RDMA_CM 为建立连接提供了一个与 RDMA 传输相关的接口。这个通信使用特定的 RDMA 设备和基于消息的数据传输。


[使用Mellanox网卡基于RDMA挂载NFS](https://sparktour.me/2023/08/24/mount-nfs-via-rdma-on-mlnx-card/)





### netApp use GDS 

https://docs.netapp.com/zh-cn/ontap/nfs-rdma/

基于 RDMA 的 NFS 利用 RDMA 适配器，可以在存储系统内存和主机系统内存之间直接复制数据，从而避免 CPU 中断和开销。

基于 RDMA 的 NFS 配置专为具有延迟敏感型或高带宽工作负载（例如机器学习和分析）的客户而设计。NVIDIA 已通过 RDMA 扩展 NFS ，以启用 GPU 直接存储（ GDS ）。GDS可通过完全绕过CPU和主内存、使用RDMA直接在存储系统和GPU内存之间传输数据、进一步加速支持GPU的工作负载。






# 字节搞定万卡集群

字节搞定万卡集群，我们可以期待国产模型了
https://mp.weixin.qq.com/s/xSE_7TKPMcJjlxywbFyL2g


【技惊四座】Meta今天发布了3.2万张GPU集群能力，至关重要就是这个以太网连接，也类似于英伟达发布的nvlink，不管二级炒不炒，这个link是关键，否则根本玩不转。

“我们已经成功地使用了RoCE和InfiniBand集群（两种方案）进行大型GenAI工作负载（包括我们在RoCE集群上正在进行的Llama 3训练）而没有网络瓶颈。” 

要注意，meta两个方案都各自实现了2.4万卡，这可能是RoCE替代IB可行性的最有力的一次证明。

另外查了下Meta这套Grand Teton系统基于2021年开始研发的ZionEX，是个GPU的全连接拓扑，用的就是RDMA over Converged Ethernet，实现GPU通过以太网完全访问彼此内存，有点类似GH200实现的256参考设计。

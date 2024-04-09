# 平安 HPC集群

RoceIP: 使用whereabouts开源技术，完成集群内Roce网络IP分配， 防止IP重复

Pod多网卡： vpc-cni+sriov

单块Nvme设备理论性能2GB/s, 每台使用2块25GB网卡做主主胚子，tcp理论带宽50Gbps
默认使用TCP协议挂载； 

方案采用2个池子， 普通池子和高性能池； 


高性能池： A800/910B ,100G 网络； 8卡 v100 25G 网络；
普通池：  带vGPU虚拟化

EHPC > EHPc in serverless (平替ECS)

EHPC in serverless : 用于推理资源池；

计算：EHPC产品，训练数据同步；
存储：平安CPFS 并行文件系统，GDS特性
网络: Roce 高性能网络


阿里DTS 的 “NAS数据传输服务”  解决两个NAS之间的数据同步 

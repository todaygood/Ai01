# nvLink

[nvlink, nvSwitch](https://www.nvidia.com/en-eu/data-center/nvlink/)

https://www.nvidia.com/en-eu/data-center/tensor-cores/


To enable high-speed, collective operations, each NVSwitch has 64 NVLink ports equipped with engines for NVIDIA Scalable Hierarchical Aggregation Reduction Protocol (SHARP)™ for in-network reductions and multicast acceleration.

NVLink is a direct GPU-to-GPU interconnect that scales multi-GPU input/output (IO) within the server. NVSwitch connects multiple NVLinks to provide all-to-all GPU communication at full NVLink speed within a single node and between nodes.    

With the combination of NVLink and NVSwitch, NVIDIA won MLPerf 1.1, the first industry-wide AI benchmark.


With NVSwitch, NVLink connections can be extended across nodes to create a seamless, high-bandwidth, multi-node GPU cluster—effectively forming a data center-sized GPU. By adding a second tier of NVLink Switches externally to the servers, future NVLink Switch Systems can connect up to 256 GPUs and deliver a staggering 57.6 terabytes per second (TB/s) of all-to-all bandwidth, making it possible to rapidly solve even the largest AI jobs. 

NVSwitch is the first on-node switch architecture to support eight to 16 fully connected GPUs in a single server node. The third-generation NVSwitch interconnects every GPU pair at an incredible 900GB/s. It supports full all-to-all communication. The GPUs can be used as a single high-performance accelerator with up to 15 petaFLOPS of deep learning compute power. 

NVLink and NVSwitch are essential building blocks of the complete NVIDIA data center solution that incorporates hardware, networking, software, libraries, and optimized AI models and applications from the NVIDIA AI Enterprise software suite and the  NVIDIA NGC™ catalog. The most powerful end-to-end AI and HPC platform, it allows researchers to deliver real-world results and deploy solutions into production, driving unprecedented acceleration at every scale. 
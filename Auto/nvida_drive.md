# nvidia 自动驾驶方案

https://developer.nvidia.cn/drive/os#DRIVEOS

NVIDIA TensorRT™ 是一个高性能深度学习推理平台。它包括硬件感知的深度学习推理优化器和运行时，可为深度学习推理应用程序提供低延迟和高吞吐量。在 NVIDIA DRIVE AGX 上， TensorRT 针对 Xavier SoC 上的专用深度学习加速器 (DLA)。

自动驾驶车辆非常复杂，需要快速准确地感知周围环境才能实时做出决策。此功能需要高性能人工智能计算来实现自动驾驶所需的各种任务，包括多级传感器数据处理、障碍物检测以及交通标志和车道识别。

CUDA 和 TensorRT 的结合使车辆上运行的 DNN 能够高速处理传感器输入。这使得车辆能够实时处理来自各种传感器的数据，从而实现 4 级和 5 级自动驾驶能力，无需人类驾驶员的监督。


## os 

自动驾驶QNX，Linux，Autosar概述

QNX是一个分布式、嵌入式、可规模扩展的实时操作系统。遵循POSIX.1 (程序接口)和POSIX.2 (Shell和工具)、部分遵循POSIX.1b(实时扩展)。

LynxOS是一个分布式、嵌入式、可规模扩展的实时操作系统，遵循POSIX.1a、POSIX.1b和POSIX.1c标准。

RT－Linux是一个嵌入式硬实时操作系统，它部分支持POSIX.1b标准。

KURT－Linux不是为嵌入式应用设计的，不同于硬实时／软实时应用，提出“严格(firm)”实时应用的概念，非常适合一些多媒体应用和ATM网络应用，KURT也同样为这些应用设计的“严格的”实时系统。


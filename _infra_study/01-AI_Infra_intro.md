---
title: "AI Infra简介"
collection: infra_study
chapter: "1. 基础介绍"
order: 1
---

在深度学习的早期，研发人员的主要精力集中在模型架构的设计上。然而，随着大语言模型（LLMs）和多模态大模型（VLMs）的参数量飙升，以及超长上下文窗口的需求激增，单张 GPU 的显存和算力早已无法满足需求。

这时候，**AI Infrastructure（AI基础设施，简称 AI Infra）** 就成为了决定模型能否成功训练、以及训练成本高低的核心壁垒。简单来说，AI Infra 是连接底层算力硬件与上层 AI 应用的“系统级桥梁”，它的终极目标是：**在有限的硬件资源下，打破“内存墙”与“通信墙”，追求极致的计算效率（MFU）和最低的系统延迟。**

![AI Infra 四层架构图](/files/infra-1/infra_architecture.png)

结合上面的架构图，一个完整的 AI Infra 技术栈自底向上通常包含以下四个核心层级：

### 1. 硬件与网络互联层 (Hardware & Networking)
正如架构图最底层所示，这是所有计算的物理底座。在大规模分布式训练中，仅仅拥有成千上万张卡是不够的，核心在于**高效的物理连接**。节点内依赖 NVLink/NVSwitch 高速互联，而跨节点的千卡集群则极度依赖 RDMA 与无损高速网络（如 InfiniBand/RoCE），它们是决定通信墙高低的关键。

### 2. 算子与底层软件层 (kernels & Compilers)
位于硬件之上的是底层软件层，负责“榨干” GPU 的每一滴性能。这里包含了 CUDA、Triton 等编程环境，以及针对显存读写瓶颈优化的**高性能算子 (Kernel)**（如 FlashAttention）。同时，像 Transformer Engine 这样的加速库，通过在底层灵活切换低精度数据格式（FP8/BF16），大幅降低显存占用并成倍提升吞吐量。

### 3. 分布式训练框架层 (Distributed Training Frameworks)
向上来到框架层，面对动辄千亿参数的模型，如何将参数、梯度、优化器状态及海量数据优雅地切分到集群中是核心挑战。以 Megatron-LM 和 DeepSpeed 为代表的框架，结合底层 NCCL 通信原语，实现了张量并行（TP）、流水线并行（PP）、数据并行（DP）的 3D 混合并行机制，并辅以激活重算（Activation Checkpointing）等技术来突破单卡显存极限。

### 4. 推理与部署层 (Inference & Serving)
最顶层直面应用，重点在于如何让模型在生产环境中快速、低成本地生成 Token。核心诉求是极致的显存管理（如 vLLM 引入的 PagedAttention 机制）、提高整体吞吐量（Throughput）并降低首字延迟（TTFT）。

---

### 结语与学习路线

AI Infra 是一个极其庞杂的领域，它的知识跨度非常大——向下深及底层的计算机体系结构、硬件网络和 C++ 级别的算子开发，向上则涵盖大规模软件系统的调度、分布式框架的设计以及 Python 层的算法实现。

对于初学者而言，一上来就一头扎进底层的硬件通信或复杂的算子编写中往往过于晦涩，且目前工业界已经提供了非常完善的底层封装，很多繁杂的细节已经被抽象抽离。因此，本系列笔记将采取**“自顶向下 (Top-Down)”**的学习路线：

![自顶向下的学习路线图](/files/infra-1/learning_route.png)

结合上方的路线图，我们的学习主要分为四个方面：

1. **稳定运行一个模型**：从最上层的分布式训练框架入手，学习如何配置环境、拉起集群任务。理解各种混合并行策略的宏观概念，先让庞大的模型在多卡环境下不 OOM、不报错地稳定跑起来。
2. **设计与更改网络结构**：在能跑通完整流程的基础上，深入框架源码，学习如何修改 Transformer 层的结构、灵活替换不同的注意力机制或加入多模态的数据交互逻辑。
3. **手写前向与反向流程**：剥离复杂的顶层框架，尝试用简单的代码手写并验证模型的前向传播（Forward）与反向传播（Backward）核心逻辑，真正吃透底层梯度是如何流动的。
4. **计算图与算子优化**：在彻底掌握上层机制和数学逻辑后，最后再向下深入，探索计算图优化策略，乃至接触更底层的算子优化（Kernel Optimization），理解如何通过压榨硬件来突破极致的性能瓶颈。

其实每个部分都非常重要，从高层的直观应用逐步深入到底层的性能压榨，算子与计算图的优化，分布式训练的容错与稳定性，但是对于学习来说，由浅及深是我们这趟 Infra 学习之旅的路径。


<script src="https://giscus.app/client.js"
        data-repo="SSSSuperC/ssssuperc.github.io"
        data-repo-id="R_kgDORcRtXw"
        data-category="General"
        data-category-id="DIC_kwDORcRtX84C3qPC"
        data-mapping="pathname"
        data-strict="0"
        data-reactions-enabled="1"
        data-emit-metadata="0"
        data-input-position="top"
        data-theme="light"
        data-lang="zh-CN"
        crossorigin="anonymous"
        async>
</script>

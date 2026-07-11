---
layout: archive
title: "简历"
permalink: /cn/cv/
author_profile: true
lang: zh
lang_alternate: /cv/
---

{% include base_path %}

## 📥 下载
[📄 下载英文简历](/files/CV_Yanxin_EN.pdf) | [📄 下载中文简历](/files/CV_Yanxin_CN.pdf)

---

## 教育经历
* **复旦大学 人工智能博士在读**

## 研究方向
* **长视频理解：** 面向长视频语义理解的检索增强生成方法，关注从浅层文本相似度匹配走向结构化、多模态推理。
* **视频大模型（VLM）：** 面向高效图文交互、流式视频推理和长上下文视频建模的模型架构设计。
* **训练基础设施：** 大规模分布式 VLM 训练、并行策略设计、激活重计算、FlashAttention 优化和集群级问题定位。

## 论文
* **ProEchoMem: Enhancing Long Video Understanding via Multi-Trace Probe-Echo Memory**
  * *共同第一作者* | SIGIR 2026
  * 提出 **PN-RAG** 框架，通过探针生成、结构化注释和精细重排序，挖掘长视频中的隐含知识连接和层级语义关系。

## 项目与工程经历
* **VLM 架构探索**
  * 设计基于 cross-attention 的图文交互模块，降低视频模型中全量 self-attention 的计算负载。
  * 引入 `cross_gate` 机制，提升跨模态交互训练过程的稳定性。

* **训练 Infra 优化**
  * 适配 Megatron 风格的并行策略和激活重计算，用于 cross-attention VLM 训练。
  * 修改 FlashAttention-3 以支持 `cross_attention_mask`，提升长视频输入下的训练效率并降低显存压力。

* **MOSS-VL 大规模训练**
  * 作为 **MOSS-VL** Core Contributor 参与模型训练与发布。
  * 负责四阶段 pretrain 以及完整 SFT 流程，包括消融实验和正式训练任务。
  * 具备千卡级集群训练经验，能够定位训练框架、数据、NCCL 通信瓶颈和死锁等问题。

## 技能
* **AI 算法：** 大语言模型（LLM）、视频大模型（VLM）、长视频理解、RAG、SFT/RL 后训练、Linear Attention。
* **训练基础设施：** 大规模分布式训练、`Megatron-LM`、`TransformerEngine`、`DeepSpeed`、`FlashAttention`/`FlashAttention-3`、TP/PP/DP 并行、激活重计算。
* **工程能力：** Python、C++（STL）、PyTorch、Linux/Bash、集群调试、NCCL 通信瓶颈定位、死锁排查。

## 未来研究方向
* **高效 VLM 训练：** 继续探索混合并行和激活重计算等优化技术，进一步扩展长视频 VLM 的可训练上下文长度和帧数上限。
* **VLM 后训练：** 研究 SFT 之后的 RL 训练与长视频任务的结合，使模型能力更贴近真实用户需求。
* **模型架构：** 探索低精度训练和 linear attention 混合架构，提升模型规模扩展能力。

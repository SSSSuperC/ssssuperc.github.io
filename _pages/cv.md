---
layout: archive
title: "Curriculum Vitae"
permalink: /cv/
author_profile: true
lang: en
lang_alternate: /cn/cv/
redirect_from:
  - /resume
---

{% include base_path %}

## 📥 Downloads
[📄 Download CV (English)](/files/CV_Yanxin_EN.pdf) | [📄 Download CV (Chinese)](/files/CV_Yanxin_CN.pdf)

---

## Education
* **Ph.D. Student in Artificial Intelligence**, Fudan University

## Research Focus
* **Long Video Understanding:** Retrieval-augmented generation for long-video semantic understanding, with an emphasis on moving beyond shallow text similarity toward structured, multi-modal reasoning.
* **Video Large Models (VLMs):** Architecture design for efficient image-text interaction, streaming video inference, and long-context video modeling.
* **Training Infrastructure:** Large-scale distributed VLM training, parallel strategy design, activation recomputation, FlashAttention optimization, and cluster-level debugging.

## Publications
* **ProEchoMem: Enhancing Long Video Understanding via Multi-Trace Probe-Echo Memory**
  * *Co-first Author* | SIGIR 2026
  * Proposed the **PN-RAG** framework to reveal implicit knowledge connections in long videos through probe generation, structured annotation, and fine-grained reranking.

## Projects & Engineering Experience
* **VLM Architecture Exploration**
  * Designed cross-attention-based image-text interaction modules to reduce the computational load of full self-attention in video models.
  * Added `cross_gate` mechanisms to improve training stability for cross-modal interaction.

* **Training Infrastructure Optimization**
  * Adapted Megatron-style parallel strategies and activation recomputation for cross-attention VLM training.
  * Modified FlashAttention-3 support for `cross_attention_mask`, improving training efficiency and reducing memory pressure for long-video inputs.

* **Large-Scale MOSS-VL Training**
  * Core contributor to **MOSS-VL**, released in April.
  * Responsible for the four-stage pretraining process and the full SFT workflow, including ablation experiments and formal training runs.
  * Experienced with thousand-GPU cluster training and debugging training-framework, data, NCCL communication, and deadlock issues.

## Skills
* **AI Algorithms:** Large Language Models (LLMs), Video Large Models (VLMs), Long Video Understanding, RAG, SFT/RL Post-training, Linear Attention.
* **Training Infrastructure:** Large-scale distributed training, `Megatron-LM`, `TransformerEngine`, `DeepSpeed`, `FlashAttention`/`FlashAttention-3`, TP/PP/DP parallelism, activation recomputation.
* **Engineering:** Python, C++ (STL), PyTorch, Linux/Bash, cluster debugging, NCCL communication bottlenecks, deadlock resolution.

## Future Research Directions
* **Efficient VLM Training:** Further explore hybrid parallelism and activation recomputation to extend the trainable context length and frame limit of long-video VLMs.
* **VLM Post-training:** Study SFT and RL training for long-video tasks, with a focus on better alignment with practical user needs.
* **Model Architecture:** Explore low-precision training and hybrid architectures that combine linear attention with existing VLM backbones.

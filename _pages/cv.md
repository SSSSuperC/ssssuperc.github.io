---
layout: archive
title: "Curriculum Vitae"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

## 📥 Downloads
[📄 Download CV (English Version)](/files/CV_Yanxin_EN.pdf) | [📄 下载个人简历 (中文版)](/files/CV_Yanxin_CN.pdf)

---

## Education
* **Ph.D. in Artificial Intelligence**, Fudan University, *Expected*
* **M.S. in Data Science**, City University of Hong Kong, *2024.09 - 2025.10*
  * **GPA: 3.76 / 4.0**
* **B.S. in Software Engineering**, Northwest University, *2020.09 - 2024.06*
  * **GPA: 3.35 / 4.0 (Top 20%)**

## Research & Work Experience
* **Research Intern** | NLP Group, Fudan University
  * *Focus: Video Large Models (VLM) & Training Infrastructure*
  * **VLM Architecture Exploration:** Designed cross-attention-based image-text interaction mechanisms, significantly reducing FLOPs and memory overhead compared to traditional full self-attention layers.
  * **Training Infra Optimization:** Optimized large-scale training using **Megatron-LM** and **Transformer Engine**. Configured 3D parallelism (TP/PP/DP) and activation checkpointing, enabling end-to-end training for ultra-long video sequences on 1,000+ GPU clusters.

* **Research Assistant** | AML Lab, City University of Hong Kong
  * *Focus: Multimodal Learning & Retrieval-Augmented Generation (RAG)*
  * **Recommender Systems:** Explored **Mixture of Experts (MoE)** for multimodal data fusion, optimizing expert routing to balance load and improve recommendation accuracy.
  * **PN-RAG Framework:** Developed content-aware retrieval strategies to address context window limitations in long-video semantic understanding, enhancing the coherence of LLM-generated responses.

## Publications
* **Beyond Shallow Retrieval: Probe-then-Note in Retrieval-Augmented Generation for Long Video Understanding**
  * *Co-first Author* | EMNLP 2025 (Under Review)
  * Introduced the PN-RAG framework to extract hierarchical structures in dense video content for deeper semantic grounding.

* **Mixture of Experts for Cross-Modal Feature Fusion in Sequential Recommendation Systems**
  * *Co-second Author* | KDD 2026 (Under Review)
  * Proposed **MoFuRec**, a three-stage fusion strategy using sparse top-k selection to optimize computational costs and expert diversity.

## Skills
* **AI Algorithms:** Large Language Models (LLMs), Multimodal Learning (VLM), RAG, Recommender Systems, Mixture of Experts (MoE).
* **Training Infrastructure:** Distributed Training on large-scale clusters (**1,000+ H200/H100 GPUs**), `Megatron-LM`, `TransformerEngine`, `DeepSpeed`, `FlashAttention`.
* **Engineering:** Python, C++ (STL), PyTorch, Linux/Bash, Cluster Debugging (NCCL communication bottlenecks, deadlock resolution).

## Awards & Honors
* **Outstanding Performance Award**, City University of Hong Kong, *2025*
* **Best Project Award**, City University of Hong Kong, *2025*
* **First-Class University Scholarship** (Twice), Northwest University, *2022, 2023*
* **ACM-ICPC University Contest Second Prize**, Northwest University, *2021*

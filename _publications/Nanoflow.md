---
title: "NanoFlow: Towards Optimal Large Language Model Serving Throughput"
collection: publications
category: arxiv
permalink: /publication/Nanoflow
excerpt: 'Throughput-oriented LLM serving system'
date: 2024-08-22
venue: 'arXiv'
slidesurl: 'http://academicpages.github.io/files/Nanoflow-slides.pdf'
paperurl: 'http://academicpages.github.io/files/Nanoflow-paper.pdf'
citation: 'Kan Zhu, Yilong Zhao, Liangyu Zhao, Gefei Zuo, Yile Gu, Dedong Xie, Yufei Gao, Qinyu Xu, Tian Tang, Zihao Ye, Keisuke Kamahori, Chien-Yu Lin, Stephanie Wang, Arvind Krishnamurthy, Baris Kasikci'
---

Abstract: The increasing usage of Large Language Models (LLMs) has resulted in a surging demand for planet-scale serving systems, where tens of thousands of GPUs continuously serve hundreds of millions of users. Consequently, throughput (under reasonable latency constraints) has emerged as a key metric that determines serving systems' performance. To boost throughput, various methods of inter-device parallelism (e.g., data, tensor, pipeline) have been explored. However, existing methods do not consider overlapping the utilization of different resources within a single device, leading to underutilization and sub-optimal performance.
We propose NanoFlow, a novel serving framework that exploits intra-device parallelism, which overlaps the usage of resources including compute, memory, and network within a single device through operation co-scheduling. To exploit intra-device parallelism, NanoFlow introduces two key innovations: First, NanoFlow splits requests into nano-batches at the granularity of operations, which breaks the dependency of sequential operations in LLM inference and enables overlapping; then, to get benefit from overlapping, NanoFlow uses an operation-level pipeline with execution unit scheduling, which partitions the device's functional units and simultaneously executes different operations in each unit. NanoFlow automates the pipeline setup using a parameter search algorithm, which enables easily porting NanoFlow to different models. We implement NanoFlow on NVIDIA GPUs and evaluate end-to-end serving throughput on several popular models such as LLaMA-2-70B, Mixtral 8x7B, LLaMA-3-8B, etc.. With practical workloads, NanoFlow provides 1.91x throughput boost compared to state-of-the-art serving systems achieving 59% to 72% of optimal throughput across ported models.
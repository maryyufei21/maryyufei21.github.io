---
title: "From Optimal to Practical: Efficient Micro-op Cache Replacement Policies for Data Center Applications"
collection: publications
category: conferences
permalink: /publication/uop
excerpt: 'micro-operation cache replacement policy'
date: 2025-03-01
venue: 'HPCA'
slidesurl: ''
paperurl: ''
citation: 'Kan Zhu, Yilong Zhao, Yufei Gao, Peter Braun, Tanvir Ahmed Khan, Heiner Litz, Baris Kasikci, Shuwen Deng'
---

Abstract: Optimizing the CPU frontend has become crucial for modern processors with intricate instruction decoding logic, especially for efficiently running planet-scale data center applications. Micro-operation (micro-op) cache is a key unit to help improve the energy efficiency of the CPU frontend. Unfortunately, we find that data center applications suffer from frequent micro-op cache misses due to the lack of an effective micro-op cache replacement policy. Developing micro-op cache-specific replacement policies is challenging, as there currently does not exist an optimal theoretical solution akin to Belady’s algorithm for conventional caches. As a result, it is unknown by how much replacement policies can be improved and how to get there.

To address these challenges, we introduce FLACK, a new near-optimal offline policy that considers the key features of the micro-op cache, such as variable and disproportional costs of micro-op cache misses and partial hits. We show that FLACK substantially outperforms Belady’s algorithm, thus establishing a new baseline for micro-op cache replacement policies. We then design FURBYS, a practical policy that mimics FLACK. FURBYS has three key components to perform cache replacement decisions: (1) it uses profiles of the whole-execution hit/miss behavior, (2) it detects locally (transiently) hot data, and (3) it selectively ignores data with profiled low hit rates. We evaluate FLACK and FURBYS using 11 data center applications and find that FLACK demonstrates a theoretical average bound of 30.21% miss reduction, achieving 4.46% greater miss reduction than Belady’s algorithm. Our practical implementation, FURBYS, provides 14.34% average miss reduction compared to LRU, which is 1.84× greater than the current state-of-the-art replacement policy, contributing to 3.10% of performance-per-watt improvement for the CPU core. On average, in terms of miss reduction and performance gain, FURBYS is equivalent to LRU policy on 1.5× micro-op cache sizes (up to 2×), which is much more costly than a replacement policy change.
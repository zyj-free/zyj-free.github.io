---
title: "Edge-ANNoy：面向资源受限设备的轻量级向量搜索"
excerpt: "设计了 Edge-ANNoy，一种面向资源受限设备的轻量级近似最近邻搜索算法，利用双锚点划分策略将内存复杂度从 O(dN) 降低至 O(N)。<br/><img src='/images/proj2.png'>"
collection: portfolio
tags:
  - 算法设计
  - 边缘计算
  - 近似最近邻搜索
---
## 📋 项目概览
**Edge-ANNoy** 是一种专为内存受限的边缘设备（如物联网网关、手机、嵌入式系统）设计的高性能近似最近邻（ANN）搜索算法。

传统的基于图的方法（如 HNSW）具有较高的内存开销（$O(d \cdot N)$），这使得它们在有限硬件上处理大规模数据集时变得不切实际。通过引入**双锚点划分策略**，Edge-ANNoy 将索引大小与向量维度解耦，实现了线性空间复杂度 $O(N)$。

**主要成就**：**1 项发明专利实审中**；合作撰写论文在投。

## 💡 核心创新：双锚点划分
其核心突破在于我们构建索引的方式：
- **传统方法**：存储完整的高维向量或复杂的图结构，导致空间复杂度为 **$O(d \cdot N)$**。
- **Edge-ANNoy 方法**：将数据投影到两个战略锚点上。这使我们只需存储标量投影值，而无需存储完整向量。
- **结果**：空间复杂度降低为 **$O(N)$**，与维度 $d$ 无关。这使得即使在仅有几 KB 可用 RAM 的设备上也能索引数百万个向量。

### 整体创新概念
下图展示了从传统的内存密集型方法到我们轻量级 Edge-ANNoy 方法的范式转变。

![Overall Innovation](/images/proj2.png)
*图：对比传统的 O(d·N) 存储方式（左，蓝色）与 Edge-ANNoy 基于投影的 O(N) 方法（右，绿色）。*

### 双锚点机制
我们的关键洞察是利用两个固定的锚点为所有数据点创建一维嵌入。

![Dual-Anchor Partitioning](/images/2-method.png)
*图：高维空间中的数据点被投影到连接“锚点 A”和“锚点 B”的直线上。仅存储生成的标量投影值，从而大幅削减内存使用。*

## 📊 实验结果
我们在多个数据集上评估了 Edge-ANNoy 与最先进基线方法（HNSW, FAISS-IVF）的性能，包括 **MillionAID**、**GUN** 和 **Hi-UCD**。
以下是 GUN、HUM 和 AID 数据集的综合结果。

<div style="display: flex; gap: 16px; overflow-x: auto; padding: 12px 0; scroll-snap-type: x mandatory;">
  <img src="/images/fig3_MillionAID.jpg" alt="Result 1" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
  <img src="/images/fig4_Hi-UCD.jpg" alt="Result 2" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
  <img src="/images/fig5_GUN.jpg" alt="Result 3" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
</div>

*图：性能对比展示了 Edge-ANNoy 在多个基准测试中的内存效率和具有竞争力的召回率。*

## 💻 技术栈
`C++` `Python` `算法设计` `Linux` `性能调优` `SIMD 优化`
<!-- 
##  Overview
**Edge-ANNoy** is a high-performance Approximate Nearest Neighbor (ANN) search algorithm designed specifically for edge devices with strict memory constraints (e.g., IoT gateways, mobile phones, embedded systems). 

Traditional graph-based methods like HNSW suffer from high memory overhead ($O(d \cdot N)$), making them impractical for large-scale datasets on limited hardware. By introducing a **Dual-Anchor Partitioning Strategy**, Edge-ANNoy decouples index size from vector dimensionality, achieving linear space complexity $O(N)$.

**Key Achievement**: **1 Invention Patent Pending**; Co-authored paper submitted to top-tier conference.

##  Core Innovation: Dual-Anchor Partitioning
The core breakthrough lies in how we structure the index:
- **Traditional Approach**: Stores full high-dimensional vectors or complex graph structures, leading to space complexity of **$O(d \cdot N)$**.
- **Edge-ANNoy Approach**: Projects data onto two strategic anchor points. This allows us to store only scalar projections rather than full vectors.
- **Result**: Space complexity is reduced to **$O(N)$**, independent of dimensionality $d$. This enables indexing millions of vectors even on devices with kilobytes of available RAM.

### Overall Innovation Concept
The figure below illustrates the paradigm shift from traditional, memory-intensive methods to our lightweight Edge-ANNoy approach.

![Overall Innovation](/images/proj2.png)
*Figure: Contrasting traditional O(d·N) storage (left, blue) with Edge-ANNoy's O(N) projection-based method (right, green).*

### The Dual-Anchor Mechanism
Our key insight is the use of two fixed anchor points to create a one-dimensional embedding for all data points.

![Dual-Anchor Partitioning](/images/2-method.png)
*Figure: Data points in a high-dimensional space are projected onto the line connecting 'Anchor A' and 'Anchor B'. Only the resulting scalar projection values are stored, drastically cutting memory usage.*

##  Experimental Results
We evaluated Edge-ANNoy against state-of-the-art baselines (HNSW, FAISS-IVF) on multiple datasets, including **MillionAID** ,**GUN** and **Hi-UCD**.
The comprehensive results across the GUN, HUM, and AID datasets are shown below.

<div style="display: flex; gap: 16px; overflow-x: auto; padding: 12px 0; scroll-snap-type: x mandatory;">
  <img src="/images/fig3_MillionAID.jpg" alt="Result 1" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
  <img src="/images/fig4_Hi-UCD.jpg" alt="Result 2" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
  <img src="/images/fig5_GUN.jpg" alt="Result 3" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
</div>

*Figure: Performance comparison showing Edge-ANNoy's memory efficiency and competitive recall across multiple benchmarks.*


##  Tech Stack
`C++` `Python` `Algorithm Design` `Linux` `Performance Tuning` `SIMD Optimization` -->

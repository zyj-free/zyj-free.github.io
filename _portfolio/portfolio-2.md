---
title: "Edge-ANNoy: Lightweight Vector Search for Resource-Constrained Devices"
excerpt: "Short description of portfolio item number 2 <br/><img src='/images/proj2.png'>"
collection: portfolio
tags:
  - Algorithm Design
  - Edge Computing
  - Approximate Nearest Neighbor
  - C++
  - Patent Pending
---

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
`C++` `Python` `Algorithm Design` `Linux` `Performance Tuning` `SIMD Optimization`

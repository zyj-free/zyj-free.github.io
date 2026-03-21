
---
title: "Precision Irrigation System: Multi-modal Sensing & Vision-Guided RL"
excerpt: "An intelligent agricultural system fusing flexible soil sensors and YOLOv8 vision (92.7% accuracy) with low-latency ICN networking. Winner of National Special Prize (TRIZ Cup) and National Bronze (Innovation Competition). <br/><img src='/images/工作流程图.png' alt='System Overview'>"
collection: portfolio
tags:
  - IoT & Embedded Systems
  - Computer Vision (YOLOv8)
  - Reinforcement Learning
  - Multi-modal Fusion
  - Award Winning
---

##  Overview
Developed a next-generation **Precision Irrigation System** that bridges the gap between physical agriculture and digital intelligence. By fusing data from **multi-modal flexible sensors** (real-time soil moisture) and **computer vision** (crop growth stage recognition), the system enables autonomous, second-level water and fertilizer dispatch.

**Key Achievements**:
-  **National Special Prize** - China TRIZ Cup (Top honor for innovation methodology)
-  **National Bronze** - China International College Students' Innovation Competition ("Internet+")
-  **National 2nd Prize** - "Challenge Cup" National College Student Extracurricular Academic Technology Competition
-  **1 Utility Model Patent** (Pending/Authorized)

##  System Architecture & Workflow
Our solution integrates four core modules into a seamless closed-loop control system:

![System Workflow](/images/工作流程图.png)
*Figure: End-to-end workflow from data acquisition (sensors/camera) to edge processing, cloud-based RL decision making, and actuator control.*

### System Block Diagram
The core of our solution is a four-layer architecture designed for efficiency and real-time response.

![System Block Diagram](/images/系统框架.png)
*Figure: The complete system stack, from perception to execution, connected by an ultra-low latency ICN network.*

### End-to-End Workflow
Data flows seamlessly through our pipeline, enabling closed-loop control.

![Workflow Diagram](/images/workflow.png)
*Figure: The operational workflow, starting from multi-modal data collection to precision actuation.*

##  Honors & Intellectual Property
All major recognitions and intellectual property are shown below.

<div style="display: flex; gap: 16px; overflow-x: auto; padding: 12px 0; scroll-snap-type: x mandatory;">
  <img src="/images/创新方法大赛获奖证书.jpg" alt="TRIZ Cup National Special Prize" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
  <img src="/images/挑战杯国家级.jpg" alt="Innovation Competition National Bronze Prize" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
  <img src="/images/互联网加省赛.jpg" alt="Challenge Cup National Second Prize or Patent Certificate" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
</div>

<p style="font-size: 0.9em; color: #666;">
Swipe horizontally to view all certificates.
</p>


##  Technical Highlights
- **Perception**: Custom flexible sensors + **YOLOv8** (92.7% accuracy).
- **Network**: **ICN protocol** achieving **≤3ms** end-to-end latency.
- **Decision**: Cloud-based **Reinforcement Learning** engine for dynamic resource optimization.
- **Impact**: Reduced water usage by **35%** and fertilizer by **20%** in field tests.

##  Tech Stack
`Python` `PyTorch` `YOLOv8` `C++` `Embedded Linux` `PCB Design` `SolidWorks` `ROS` `ICN` `Deep Reinforcement Learning`

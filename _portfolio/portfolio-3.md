---
title: "精准灌溉系统：多模态感知与视觉引导强化学习"
excerpt: "一套融合了柔性土壤传感器与 YOLOv8 视觉识别（准确率 92.7%）的智能农业系统，采用低延迟 ICN 组网。荣获全国特等奖（TRIZ 杯）及全国铜奖（互联网+大赛）。<br/><img src='/images/kuangjia.png' alt='系统概览'>"
collection: portfolio
tags:
  - 物联网与嵌入式系统
  - 计算机视觉 (YOLOv8)
  - 强化学习
  - 多模态融合
  - 获奖项目
---

## 📋 项目概览
开发了一套新一代**精准灌溉系统**，弥合了实体农业与数字智能之间的鸿沟。通过融合**多模态柔性传感器**（实时土壤湿度监测）与**计算机视觉**（作物生长阶段识别）的数据，该系统实现了自主的秒级水肥调度。

**主要成就**：
- **全国特等奖** - 中国 TRIZ 杯（创新方法论最高荣誉）
- **全国铜奖** - 中国国际大学生创新大赛（“互联网+”）
- **国家二等奖** - “挑战杯”全国大学生课外学术科技作品竞赛
- **1 项实用新型专利**（已受理/授权）

## 🏗️ 系统架构与工作流
我们的解决方案将四个核心模块集成为一个无缝的闭环控制系统：

![System Workflow](/images/GONGZUO.png)
*图：从数据采集（传感器/相机）到边缘处理、云端强化学习决策以及执行器控制的端到端工作流。*

### 系统框图
我们方案的核心是一个为效率和实时响应而设计的四层架构。

![System Block Diagram](/images/kuangjia.png)
*图：完整的系统栈，从感知到执行，由超低延迟的 ICN 网络连接。*

### 端到端流程
数据在我们的流水线中无缝流动，实现闭环控制。

![Workflow Diagram](/images/workflow.png)
*图：操作工作流，从多模态数据采集开始，到精准执行结束。*

## 🏆 荣誉与知识产权
以下是所有的主要奖项和知识产权证明。

<div style="display: flex; gap: 16px; overflow-x: auto; padding: 12px 0; scroll-snap-type: x mandatory;">
  <img src="/images/TRIZ.jpg" alt="TRIZ Cup National Special Prize" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
  <img src="/images/challange-cup.jpg" alt="Innovation Competition National Bronze Prize" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
  <img src="/images/hu.jpg" alt="Challenge Cup National Second Prize or Patent Certificate" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
</div>

<p style="font-size: 0.9em; color: #666;">
左右滑动查看所有证书。
</p>


## 💡 技术亮点
- **感知层**：定制柔性传感器 + **YOLOv8**（准确率 92.7%）。
- **网络层**：**ICN 协议**实现**毫秒级**端到端延迟。
- **决策层**：基于云端的**强化学习**引擎，用于动态资源优化。
- **成效**：实地测试显示节水**35%**，节肥**20%**。

## 💻 技术栈
`Python` `PyTorch` `YOLOv8` `C++` `ROS` `ICN` `深度强化学习`



<!-- ---
title: "Precision Irrigation System: Multi-modal Sensing & Vision-Guided RL"
excerpt: "An intelligent agricultural system fusing flexible soil sensors and YOLOv8 vision (92.7% accuracy) with low-latency ICN networking. Winner of National Special Prize (TRIZ Cup) and National Bronze (Innovation Competition). <br/><img src='/images/kuangjia.png' alt='System Overview'>"
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

![System Workflow](/images/GONGZUO.png)
*Figure: End-to-end workflow from data acquisition (sensors/camera) to edge processing, cloud-based RL decision making, and actuator control.*

### System Block Diagram
The core of our solution is a four-layer architecture designed for efficiency and real-time response.

![System Block Diagram](/images/kuangjia.png)
*Figure: The complete system stack, from perception to execution, connected by an ultra-low latency ICN network.*

### End-to-End Workflow
Data flows seamlessly through our pipeline, enabling closed-loop control.

![Workflow Diagram](/images/workflow.png)
*Figure: The operational workflow, starting from multi-modal data collection to precision actuation.*

##  Honors & Intellectual Property
All major recognitions and intellectual property are shown below.

<div style="display: flex; gap: 16px; overflow-x: auto; padding: 12px 0; scroll-snap-type: x mandatory;">
  <img src="/images/TRIZ.jpg" alt="TRIZ Cup National Special Prize" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
  <img src="/images/challange-cup.jpg" alt="Innovation Competition National Bronze Prize" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
  <img src="/images/hu.jpg" alt="Challenge Cup National Second Prize or Patent Certificate" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
</div>

<p style="font-size: 0.9em; color: #666;">
Swipe horizontally to view all certificates.
</p>


##  Technical Highlights
- **Perception**: Custom flexible sensors + **YOLOv8** (92.7% accuracy).
- **Network**: **ICN protocol** achieving **ms-level** end-to-end latency.
- **Decision**: Cloud-based **Reinforcement Learning** engine for dynamic resource optimization.
- **Impact**: Reduced water usage by **35%** and fertilizer by **20%** in field tests.

##  Tech Stack
`Python` `PyTorch` `YOLOv8` `C++` `ROS` `ICN` `Deep Reinforcement Learning` -->

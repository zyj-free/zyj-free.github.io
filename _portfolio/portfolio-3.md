---
title: "施半功倍：人参仿野化精准灌施系统系统"
excerpt: "针对人参种植痛点研发的智能化系统。融合光电多模态传感、YOLOv8视觉识别与RLT决策模型，配合LAD光伏自动混肥技术。荣获全国特等奖（TRIZ杯）及多项国家级荣誉。<br/><img src='/images/kuangjia.png' alt='系统概览'>"
collection: portfolio
tags:
  - 物联网与嵌入式系统
  - 计算机视觉 (YOLOv8)
  - 多模态融合
---

## 📋 项目背景与痛点
当前人参种植业面临“经验灌施、低效低产”的困境。传统模式存在三大核心痛点：
1.  **无序灌施导致流失**：次生代谢紊乱，湿度控制不当，水肥利用率低。
2.  **过量干预生态失衡**：腐殖质层孔隙度降低，根腐病频发，林下参存苗率跌破55%。
3.  **低质人参供过于求**：传统非林地人参产量过饱和，但高品质野参稀缺，农户面临滞销困境。

市面上的灌施设备存在“拙、窄、粗、低”的问题（自动化低、适用范围窄、控制粗放、性价比低），无法满足山乡人参产业的复杂需求。

## 💾 数据集构建与模型评估
为了适应复杂多变的林下光照环境，我们构建了专用的**人参生长监测数据集**，并针对边缘设备进行了模型轻量化评估。

### 数据集规模
- **数据来源**：团队深入吉林人参种植区，历时 3 个月实地采集。
- **数据总量**：**5,000+ 张** 高分辨率原始图像。
- **覆盖场景**：涵盖不同生长周期（出苗、开花、红果）、不同光照条件（强光、阴影、夜间）及不同病害特征。
- **标注信息**：包含边界框标注与生长状态分类标签，确保模型能精准识别作物长势。

### 模型大小与推理性能
考虑到田间设备算力有限，我们选用 **YOLOv8** 作为基准模型，并进行了针对性优化：
- **模型体积**：经过剪枝与量化，模型文件大小压缩至 **< 20MB**，极低存储占用。
- **推理速度**：在边缘计算模块（如 Jetson Nano/RK3588）上推理速度达到 **15 FPS**，满足实时监测需求。
- **准确率**：在自建测试集上 mAP@0.5 达到 **92%**，有效平衡了精度与速度。


## 🏗️ 解决方案与系统架构
本项目研发了一套**人参仿野化精准灌施系统**，通过四大创新点实现从“经验种植”到“数据驱动”的跨越。整个系统的部署包非常轻，边缘端不到 30MB，非常适合在农业野外环境下的低成本硬件上落地。”
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


### 核心创新点

#### 1. 光电融合多模态传感结构
- **技术原理**：采用光电融合的多模态柔性传感器，后端机械螺旋杆可自由伸缩，形成三维坐标系。
- **功能**：能够检测有机质、盐碱度等土壤情况，以及作物根系生长状况。
- **能力**：支持检测19种作物生长数据及20余种土壤墒情数据。

#### 2. YOLOv8 实时检测算法
- **核心算法**：基于 **YOLOv8** 架构，结合图像二维去噪、自适应二值化（大津法）及腐蚀膨胀运算。
- **性能指标**：
    - **准确率**：92%
    - **识别速率**：15次/秒
    - **单次识别量**：6株作物
- **应用**：快速精准识别作物与长势，平滑图像边界，消除环境光线干扰。

#### 3. RLT 综合决策与 LAD 光伏混肥
- **RLT 决策模型**：基于采集数据计算最佳水肥灌施比例，计算耗时仅 **8ms**，预测精度达 **97%** (AUC 0.89)。
- **LAD 光伏系统**：利用光伏能源实现水肥液精准混合，混合肥料控制精度达 **0.5%**，能耗降低 **50%**。

#### 4. 自研 ICN 网络架构
- **架构优势**：5G低时延快速计算，通过网络边缘进行数据缓存和计算。
- **性能表现**：传输延时 **≤3ms**，响应时长 **<1s**，算力提升 **50%**。
- **并发能力**：最高支持100台农机同时接入。



## 🏆 荣誉与知识产权
本项目凭借创新的技术架构和显著的实地效果，获得了多项国家级荣誉：

- **全国特等奖** - 中国TRIZ杯大学生创新方法大赛
- **全国铜奖** - 中国国际“互联网+”大学生创新创业大赛
- **国家二等奖** - “挑战杯”全国大学生课外学术科技作品竞赛
- **知识产权**：拥有多项实用新型专利及计算机软件著作权（涵盖感知结构与决策系统）。

以下是所有的主要奖项和知识产权证明。

<div style="display: flex; gap: 16px; overflow-x: auto; padding: 12px 0; scroll-snap-type: x mandatory;">
  <img src="/images/TRIZ.jpg" alt="TRIZ Cup National Special Prize" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
  <img src="/images/challange-cup.jpg" alt="Innovation Competition National Bronze Prize" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
  <img src="/images/hu.jpg" alt="Challenge Cup National Second Prize or Patent Certificate" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
  <img src="/images/huanli.png" alt="Challenge Cup National Second Prize or Patent Certificate" style="width: 85%; max-width: 520px; height: auto; flex: 0 0 auto; border: 1px solid #eee; border-radius: 8px; scroll-snap-align: start;">
</div>

<p style="font-size: 0.9em; color: #666;">
左右滑动查看所有证书。
</p>


## 📊 实测成效
- **识别精准**：作物识别准确率达92%，满足实时作业需求。
- **决策高效**：RLT模型毫秒级响应，配合LAD系统实现水肥精准配比。
- **连接稳定**：ICN架构保障了复杂山林环境下的低延迟通信。

## 💻 技术栈
`Python` `PyTorch` `YOLOv5` `C++` `ICN` `光伏控制` `多模态传感`


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

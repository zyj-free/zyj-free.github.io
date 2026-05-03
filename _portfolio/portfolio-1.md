---
title: "点格棋 AI：利用深度强化学习与 MCTS 攻克稀疏奖励难题"
excerpt: "构建了一款结合深度强化学习与蒙特卡洛树搜索的点格棋 AI，成功解决了游戏过程中的稀疏奖励问题，并斩获国家级奖项。<br/><img src='/images/iemian.png'>"
collection: portfolio
tags:
  - 深度强化学习
  - 蒙特卡洛树搜索
  - 博弈论
  - Python
  - PyTorch
---

## 📋 项目概览
开发了一款**点格棋**自主智能体，其性能超越了传统的启发式机器人。通过将**深度强化学习**与**蒙特卡洛树搜索**相结合，我们成功解决了长程博弈中**稀疏奖励**这一关键挑战。

**主要成就**：在中国计算机博弈锦标赛中荣获**全国一等奖**并斩获亚军。

## ⚠️ 面临的挑战

在点格棋这类具有稀疏奖励特性的游戏中，智能体的学习过程面临着根本性的挑战。奖励信号（即占领一个方格）并非在每一步都出现，而是集中在某些关键动作之后。这使得标准的强化学习智能体在广阔的搜索空间中，难以通过简单的试错法将最终的胜利与早期的策略性布局联系起来，导致学习效率极低。
传统的解决方案，如 AlphaZero 框架，虽然强大，但在应对此类问题时仍存在两个核心瓶颈：

1.  **回报信号的极端稀疏性 (Extremely Sparse Reward Signal)**
    AlphaZero 类方法通常只在整局游戏结束时提供一个二元奖励（胜/负）。这种“终局判决”式的反馈机制，使得智能体无法评估中间步骤的质量。它不知道某一步是精妙的伏笔还是致命的失误，只能得到最终结果的笼统评判。这就像让一个学生解一道复杂的数学题，却不告诉他哪一步算错了，只给一个最终的分数，极大地延缓了学习进程。

2.  **昂贵的数据利用率 (Inefficient Data Utilization)**
    在 AlphaZero 的训练循环中，每一次 MCTS 搜索都是一次巨大的计算开销。然而，这个过程会产生海量的中间节点数据——每一个被访问的节点都包含了对该局面价值的宝贵评估（Q 值）和策略先验（Pi）。但标准做法是，仅利用根节点的聚合策略来训练神经网络，而将搜索树中所有其他节点的信息全部丢弃。这是一种极其昂贵且低效的数据使用方式，相当于从一座金矿中只取走一小块金子，却扔掉了其余所有的矿石。


## 🛠️ 方法论
我们的解决方案引入了一种混合架构：

1.  **自博弈迭代框架**：智能体通过与自己对弈生成多样化的训练数据，并持续更新策略网络。
2.  **混合搜索策略**：
    *   **用于探索的蒙特卡洛树搜索**：利用神经网络作为先验知识，高效地引导树搜索。
    *   **残局定理**：我们将点格棋特有的数学定理编码进叶节点评估中，确保在最后阶段实现完美博弈。
3.  **逆向训练架构**：一种新颖的训练循环，从已知的残局状态向早期动作反向传播价值，从而加速收敛。
4.  **哈希存储**：实现了置换表来缓存访问过的状态，减少了约 40% 的冗余计算。


### 💼 个人主要职责

*   **训练过程优化**：协助实现了基于两阶段自博弈的强化学习训练框架。该框架在第一阶段采用逆向采样优先训练价值模型，第二阶段引入全局奖励以优化策略模型。
*   **策略评估和搜索算法优化**：通过 ELO 评分可视化模型性能，并采用数据增强技术筛选高质量数据以提升模型鲁棒性。


## 📊 结果
![Result](/images/iemian.png)
*BoxesZero 与 AlphaZero 在不同训练时长下的准确率对比，并在各个游戏阶段进行了评估。结果表明，BoxesZero 能够在显著更短的训练时间内达到高水平的熟练度。*


1.  **消融实验**：针对几种关键技术拆分为 4 组进行消融实验，结果证明了所提技术的有效性。
2.  **最终性能**：比较了 BoxesZero 和 AlphaZero 在不同训练时间检查点（ckpt）于不同棋局阶段的准确率。结果显示 BoxesZero 可以在更短的时间内达到高水平棋力。


## 🏆 获得认可
![Award Certificate](/images/博弈国奖2.png)

*2025年中国大学生计算机博弈大赛全国一等奖*

**论文发表**：点格棋智能体研究论文已于 SCI 期刊《Entropy》（JCR Q2）见刊。
> Niu, X.; Liu, Q.; Chen, W.; Zheng, Y.; Jin, Z. BoxesZero: An Efficient and Computationally Frugal Dots-and-Boxes Agent. *Entropy* 2025, 27(3), 285.

## 💻 技术栈
`Python` `PyTorch` `NumPy` `MCTS` `Git`

<!-- ##  Overview
Developed an autonomous agent for the game of **Dots and Boxes** that outperforms traditional heuristic bots. By integrating **Deep Reinforcement Learning (DRL)** with **Monte Carlo Tree Search (MCTS)**, we successfully addressed the critical challenge of **sparse rewards** in long-horizon gameplay.

**Key Achievement**: Won **National 1st Prize** at the China Computer Game Championship (Top-tier national competition).

##  The Challenge
In Dots and Boxes, rewards (scoring a box) only occur at specific moments, making it difficult for standard RL agents to learn effective strategies through trial and error. Traditional MCTS also struggles without a strong evaluation function in the endgame.

##  Methodology
Our solution introduces a hybrid architecture:

1.  **Self-Play Iterative Framework**: The agent plays against itself to generate diverse training data, continuously updating the policy network.
2.  **Hybrid Search Strategy**:
    *   **MCTS for Exploration**: Uses the neural network as a prior to guide tree search efficiently.
    *   **Endgame Theorems**: We encoded mathematical theorems specific to Dots and Boxes into the leaf node evaluation, ensuring perfect play in the final stages.
3.  **Reverse Training Architecture**: A novel training loop that backpropagates values from known endgame states to earlier moves, accelerating convergence.
4.  **Hash Storage**: Implemented a transposition table to cache visited states, reducing redundant computation by ~40%.


##  Results
![Result](/images/iemian.png)
*Comparison of accuracy between BoxesZero and AlphaZero checkpoints trained for different durations, evaluated across various game stages. Results demonstrate that BoxesZero achieves high-level proficiency in significantly less training time.*

##  Recognition
![Award Certificate](/images/博弈国奖2.png)

*Official certificate from the 2025 China University Student Computer Game Competition — awarded 2nd Place (National First Class Equivalent).*
##  Tech Stack
`Python` `PyTorch` `NumPy` `MCTS` `Git` -->

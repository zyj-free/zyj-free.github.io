---
title: "Dots and Boxes AI: Mastering Sparse Rewards with Deep RL & MCTS"
excerpt: "Built a Dots and Boxes AI that combines Deep Reinforcement Learning with Monte Carlo Tree Search to tackle sparse-reward gameplay and achieve award-winning performance.<br/><img src='/images/iemian.png'>"
collection: portfolio
tags:
  - Deep Reinforcement Learning
  - MCTS
  - Game Theory
  - Python
  - PyTorch
---

##  Overview
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
`Python` `PyTorch` `NumPy` `MCTS` `Git`

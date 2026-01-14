---
layout: page
title: Overview
permalink: /
weight: 1
---

<div style="text-align: center; display: flex; width: 100%; justify-content: space-evenly; align-items: center; gap: 1em; padding: 2em">
  <img style="width: 30%;" src="https://github.com/Open-Finance-Lab/AI4Science-Art_Contest_2026/blob/main/docs/assets/logos/ieee-logo.png?raw=true" alt="IEEE Logo">
  <img style="width: 20%;" src="https://github.com/Open-Finance-Lab/AI4Science-Art_Contest_2026/blob/main/docs/assets/logos/columbiau.jpeg?raw=true" alt="Columbia Logo">
</div>


## Introduction

Recent advances in AI, particularly reinforcement learning, have enabled data-driven approaches to challenging combinatorial optimization and physics problems, including Max-Cut and the search for ground states of Ising spin systems [1–6]. These problems are central to graph optimization and statistical physics and serve as standard benchmarks for evaluating learning-based optimization methods. Building on prior work in learning combinatorial optimization algorithms [2,6] and applying reinforcement learning to spin systems [1,3,4,5], this track encourages the development of AI agents that achieve strong performance, generalization, and scalability on benchmarks.

We design two challenge tasks that allow participants to explore learning-based optimization methods and contribute to AI-driven scientific discovery. We welcome students, researchers, and engineers interested in AI, physics, and optimization to participate.

## Tasks

Each team can choose to participate in one or both tasks. Awards and recognitions will be given for each task. 

### Task I

#### Dataset

#### Goal


---

### Task II: Finding Ground State Energy of Ising Model

This task benchmarks the reliability of AI agents for scientific simulation, specifically for the Ising model. Finding the ground state energy of the Ising model is computationally difficult but fundamental to simulating complex physical systems. Participants are expected to develop reinforcement learning or foundation models that will be evaluated on their ability to efficiently locate ground states in large-scale Ising spin lattices.

- **Goal**: Minimize the Hamiltonian energy $H$ on large-scale Ising lattices.
- **Dataset**: We utilize a compiled standard dataset of [Ising model instances](https://huggingface.co/datasets/SecureFinAI-Lab/Ising_Model_Instances) on Huggingface.
- **Metric**: We provide an evaluator program in the starter kit that calculates the geometric mean across results.

Starter kit will come soon.

---

<p style="font-size: 14px;">
[1] Lin, Levy, et al. "Reinforcement Learning for Ising Models: Datasets and Benchmark." <em>NeurIPS 2025 Workshop on Machine Learning and the Physical Sciences</em>. [<a href="https://ml4physicalsciences.github.io/2025/files/NeurIPS_ML4PS_2025_245.pdf">NeurIPS 2025 Workshop</a>]
</p>
  
<p style="font-size: 14px;">
[2] Liu, Xiao-Yang, and Zhu, Ming. "K-Spin Ising Model for Combinatorial Optimizations over Graphs: A Reinforcement Learning Approach." <em>NeurIPS 2023 Workshop on Optimization for Machine Learning</em>. [<a href="https://opt-ml.org/papers/2023/paper2.pdf">NeurIPS 2023 Workshop</a>]
</p>

<p style="font-size: 14px;">
[3] Hibat-Allah, Mohamed, et al. "Variational Neural Annealing." <em>Nature Machine Intelligence</em> (2021). [<a href="https://www.nature.com/articles/s42256-021-00401-3">Nature</a>]
</p>

<p style="font-size: 14px;">
[4] Mills, Kyle, et al. "Finding the Ground State of Spin Hamiltonians with Reinforcement Learning." <em>Nature Machine Intelligence</em> (2020). [<a href="https://www.nature.com/articles/s42256-020-0226-x">Nature</a>]
</p>

<p style="font-size: 14px;">
[5] Fan, Changjun, et al. "Searching for Spin Glass Ground States through Deep Reinforcement Learning." <em>Nature Communications</em> (2023). [<a href="https://www.nature.com/articles/s41467-023-36363-w">Nature</a>]
</p>

<p style="font-size: 14px;">
[6] Barrett, Thomas, et al. "Exploratory Combinatorial Optimization with Reinforcement Learning." <em>Proceedings of the AAAI Conference on Artificial Intelligence</em> (2020). [<a href="https://ojs.aaai.org/index.php/AAAI/article/view/5723">AAAI</a>]
</p>

## Contact
Contact email: rlsolvercontest@outlook.com

Contestants can communicate any questions on 
* [Discord](https://discord.gg/QekXz9V63p).
* QQ Group: 922523057
* WeChat Group: 
<div style="text-align: center; display: flex; justify-content: center; padding: 2em;">
  <img 
    style="width: 20%;" 
    src="https://raw.githubusercontent.com/Open-Finance-Lab/RLSolver_Contest_2025/main/docs/assets/pictures/wechat_group.jpg" 
    alt="WeChat Group">
</div>






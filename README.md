# AI for Science and Art Contest 2026

This repository contains the website content and starter materials for the **AI for Science and Art Contest 2026**.

## Outline
  - [Overview](#overview)
  - [Task 1: Graph Max-Cut with Parallel RL Agents](#task-1-graph-max-cut-with-parallel-rl-agents)
  - [Task 2: Finding Ground State Energy of Ising Model](#task-2-finding-ground-state-energy-of-ising-model)
  - [Paper Submission Requirements](#paper-submission-requirement)
  - [Resources](#resources)

## Overview

The AI4Science&Art track explores the effectiveness of AI-driven scientific discovery, including Reinforcement Learning, Foundation Models. and Neuro-symbolic approaches, to solve complex problems in physics and mathematics.

We encourage the development of robust agents that demonstrate:
- Scalability: The ability to handle large, complex systems.
- Generalization: The ability to adapt to new, unseen data.
- Performance: The ability to find optimal solutions efficiently.

We host two tasks to promote interdisciplinary solutions across physics, optimization, and AI-driven discovery.

Each team can choose to participate in one or both tasks. Awards and recognitions will be given for each task.

## Task 1: Graph Max-Cut with Parallel RL Agents

Develop GPU-accelerated RL agents to solve the Max-Cut problem on large graphs. This task focuses on learning generalizable solutions across different graph distributions (e.g., BA, ER, PL).  
Starter kit coming soon.

## Task 2 Finding Ground State Energy of Ising Model

This task benchmarks the reliability of AI agents for scientific simulation, specifically for the Ising model. Finding the ground state energy of the Ising model is computationally difficult but fundamental to simulating complex physical systems. Participants are expected to develop reinforcement learning or foundation models that will be evaluated on their ability to efficiently locate ground states in large-scale Ising spin lattices.

- **Goal**: Minimize the Hamiltonian energy $H$ on large-scale Ising lattices.
- **Dataset**: We utilize a compiled standard dataset of [Ising model instances](https://huggingface.co/datasets/SecureFinAI-Lab/Ising_Model_Instances) on Huggingface.
- **Metric**: We provide an evaluator program in the starter kit that calculates the geometric mean across results.

Starter kit is available at  
[GitHub – Task II Starter Kit](https://github.com/Open-Finance-Lab/AI4Science-Art_Contest_2026/tree/main/src).

## Paper Submission Requirements
Each team should submit short papers with 3 complimentary pages and up to 2 extra pages, including all figures, tables, and references. The paper submission is through [the special track](https://www.cloud-conf.net/datasec/2026/ids/AI4Science&Art.html) and should follow its instructions. Please include “AI for Science and Art Contest 1/2” in your abstract.


## Resources
[RLSolver Contest Documentation](https://rlsolver-competition.readthedocs.io/en/latest/rlsolver_contest_2025/train_test.html)

RLSolver
* [RLSolver Github Repo](https://github.com/Open-Finance-Lab/RLSolver)
* [RLSolver docs](https://rlsolvers.readthedocs.io/index.html)

RL4Ising
* [RL4Ising Github Repo](https://github.com/Open-Finance-Lab/RL4Ising)
* [RL4Ising docs](https://rl4ising-docs.readthedocs.io/en/latest/)

Relevant repositories and datasets:
* RLSolver Codebase (coming soon)
* GPU simulation environments (CUDA-based)
* Graph datasets (BA, ER, PL)
* Ising model generator and reference solvers


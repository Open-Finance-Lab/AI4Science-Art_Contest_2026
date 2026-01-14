# AI for Science and Art Contest 2026

This repository contains the website content and starter materials for the **AI for Science and Art Contest 2026**.

## Outline
  - [Overview](#overview)
  - [Task 1](#task-1)
  - [Task 2](#task-2-finding-ground-state-energy-of-ising-model)
  - [Paper Submission Requirements](#paper-submission-requirements)
  - [Resources](#resources)

## Overview

Each team can choose to participate in one or both tasks. Awards and recognitions will be given for each task.

## Task 1

## Task 2 Finding Ground State Energy of Ising Model

This task benchmarks the reliability of AI agents for scientific simulation, specifically for the Ising model. Finding the ground state energy of the Ising model is computationally difficult but fundamental to simulating complex physical systems. Participants are expected to develop reinforcement learning or foundation models that will be evaluated on their ability to efficiently locate ground states in large-scale Ising spin lattices.

- **Goal**: Minimize the Hamiltonian energy $H(\sigma)$ on large-scale Ising lattices.
- **Dataset**: We utilize a compiled standard dataset of [Ising model instances](https://huggingface.co/datasets/SecureFinAI-Lab/Ising_Model_Instances) on Huggingface.
- **Metric**: We provide an evaluator program in the starter kit that calculates the geometric mean across results.

Starter kit will come soon.

## Paper Submission Requirements
Each team should submit short papers with 3 complimentary pages and up to 2 extra pages, including all figures, tables, and references. The paper submission is through [the special track](https://www.cloud-conf.net/datasec/2026/ids/AI4Science&Art.html) and should follow its instructions. Please include “RLSolver Contest Task 1/2” in your abstract.


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


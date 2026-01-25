# AI for Science and Art Task 2 Dataset & Starterkit

## Goal
This task benchmarks the reliability of AI agents for scientific simulation, specifically for the Ising model. Finding the ground state energy of the Ising model is computationally difficult but fundamental to simulating complex physical systems. Participants are expected to develop reinforcement learning or foundation models that will be evaluated on their ability to efficiently locate ground states in large-scale Ising spin lattices.

Your goal is to minimize Hamiltonian energy $H$ on large-scale Ising lattices.

## Dataset

We provide a dataset of challenging Spin Glass instances featuring geometric frustration, large edge weights, large scale, and high dimensionality.

Dataset will come soon.

## Starterkit
Our starterkit ships two reference ML solvers:

| Solver | Paper | Original authors | Our fork |
|--------|-------|------------------|----------|
| **MCPG** | *Monte Carlo Policy Gradient Method for Binary Optimization* (Cheng Chen et al., 2023) | <https://github.com/optsuite/mcpg> | `src/Task_2/starterkit/MCPG/mcpg.py` |
| **VCA** | *Variational Neural Annealing* (Mohamed Hibat-Allah et al., 2021) | <https://github.com/VectorInstitute/VariationalNeuralAnnealing> | `src/Task_2/starterkit/VCA/vca.py` |


### MCPG Quickstart
Environment setup: We recommend conda for the most convenient installation.
```
conda env create -f envs/mcpg_environment.yaml
```
Usage:
```
python mcpg.py ising_default.yaml [problem instance]
```
Example Ouput:
```
> python mcpg.py ising_default.yaml ../../dataset/EA/EA_10x10/10x10_uniform_seed1.txt

o -78.650
o -78.650
o -78.650
o -78.650
o -78.650
o -78.650
OUTPUT: -78.650406
DATA LOADING TIME: 4.3900
MCPG RUNNING TIME: 14.1647
```
Configuration of Local Search and Sampling frequency is located in `src/Task_2/starterkit/MCPG/ising_default.yaml`.


### VCA Quickstart
Environment setup: We recommend conda for the most convenient installation.
```
conda env create -f envs/vca_environment.yaml
```
Usage:
```
python vca.py [problem instance]
```
Example Ouput:
```
> python vca.py ../../dataset/EA/EA_10x10/10x10_uniform_seed1.txt

mean(E): -33.5433660848712, mean(F): -154.89824287379463, var(E): 73.85991566131288, var(F): 1.9722050905523278, #samples 50, #Training step 995
Temperature:  2
Magnetic field:  0
Elapsed time is = 136.02788472175598  seconds

Annealing step: 0.0/16
mean(E): -30.45648157385779, mean(F): -154.68102832935563, var(E): 66.25562318673148, var(F): 2.823127462608233, #samples 50, #Training step 1000
Temperature:  2.0
Magnetic field:  0.0
Elapsed time is = 136.66887617111206  seconds

Annealing step: 1.0/16
mean(E): -30.350349655435977, mean(F): -146.9989938326911, var(E): 69.15800262173676, var(F): 4.390464855014674, #samples 50, #Training step 1005
Temperature:  1.875
Magnetic field:  0.0
Elapsed time is = 137.31043696403503  seconds
```
Configuration of Wavefunction RNN and Simulated Annealing Samping procedure is located in `src/Task_2/starterkit/VCA/config.py`.

## Directory Layout
```
    ├── dataset/            : 
    |
    └── starterkit/
        ├── envs/
        |   ├── mcpg_enviroment.yaml    : Conda environment file for MCPG.
        |   ├── vca_enviroment.yaml     : Conda environment file for VCA.
        |
        ├── MCPG/
        |   ├── dataloader.py       : Data loader for MCPG to input the problem instance.
        |   ├── ising_default.yaml  : Configuration file Local Search and sampling for Ising instances.
        |   ├── mcpg.py             : Main file to run MCPG on specific problem instance.
        |   ├── model.py            : The probabilistic model to output the mean-field distribution.
        |   └── sampling.py         : The sampling procedure combining with the local search 
        |                             algorithm in MCPG. 
        └── VCA/
            ├── config.py       : Configuration file for model and sampling procedure.
            ├── DilatedRNN.py   : The Wavefunction RNN to output the Boltzmann distrubtion samples. 
            ├── utils.py        : Helper functions to calculate Hamiltonian energy.
            └── vca.py          : Main file to run VCA on specific problem instance.  
```
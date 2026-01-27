# AI for Science and Art Task 2: Starterkit

## Goal

This task benchmarks the reliability of AI agents for scientific simulation, specifically for the Ising model. Finding the ground state energy of the Ising model is computationally difficult but fundamental to simulating complex physical systems. Participants are expected to develop reinforcement learning or foundation models that will be evaluated on their ability to efficiently locate ground states in large-scale Ising spin lattices.

Your goal is to minimize Hamiltonian energy on large-scale Ising lattices. 

$$
H(\sigma) = - \sum_{i<j} J_{ij} \sigma_i \sigma_j
$$


## Starterkit

Our starterkit ships two reference ML solvers:

| Solver         | Paper                                                                                    | Original authors                                                                                                            | Our fork                               |
| -------------- | ---------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | -------------------------------------- |
| **MCPG** | *Monte Carlo Policy Gradient Method for Binary Optimization* (Cheng Chen et al., 2023) | [https://github.com/optsuite/mcpg](https://github.com/optsuite/mcpg)                                                           | `src/Task_2/starterkit/MCPG/mcpg.py` |
| **VCA**  | *Variational Neural Annealing* (Mohamed Hibat-Allah et al., 2021)                      | [https://github.com/VectorInstitute/VariationalNeuralAnnealing](https://github.com/VectorInstitute/VariationalNeuralAnnealing) | `src/Task_2/starterkit/VCA/vca.py`   |

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

```
lr_init: 0.25           # Inital learning rate
regular_init: 0         # Inital regularization strength
sample_epoch_num: 8     # Number of trainng epcohs between MCMC sampling
max_epoch_num: 400      # Total number of epochs
reset_epoch_num: 80     # Number of epochs between model's parameter reset
total_mcmc_num: 130     # Number of parallel MCMC samples
repeat_times: 120       # Number of times the best solution is replicated
num_ls: 3               # Number of Local Search steps
```

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

```
self.num_units = 40                     # Number of hidden memory units per layer
self.num_layers = int(sqrt(N))          # Number of RNN layers
self.activation_function = tf.nn.elu    # Non-linear activation function for the RNN cell

self.numsamples = 50                    # Number of samples used for each training step
self.lr = 5*(1e-4)                      # Learning rate
self.T0 = 2                             # Initial temperature
self.Bx0 = 0                            # Initial magnetic field
self.num_warmup_steps = 1000            # Number of warmup steps
self.num_annealing_steps = 2**8         # Number of annealing steps
self.num_equilibrium_steps = 5          # Number of training steps after each annealing step
```

## Directory Layout

```
    ├── dataset/            : Provided dataset of Ising model instances
    |
    └── starterkit/
        ├── envs/
        |   ├── mcpg_enviroment.yaml    : Conda environment file for MCPG.
        |   └── vca_enviroment.yaml     : Conda environment file for VCA.
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

## References

Chen, Cheng & Chen, Ruitao & Li, Tianyou & Ao, Ruicheng & Wen, Zaiwen. (2025). A Monte Carlo Policy Gradient Method with Local Search for Binary Optimization. Mathematical Programming. 10.1007/s10107-025-02277-2. https://arxiv.org/abs/2307.00783

Hibat-Allah, M., Inack, E.M., Wiersema, R. et al. Variational neural annealing. Nat Mach Intell 3, 952–961 (2021). https://doi.org/10.1038/s42256-021-00401-3

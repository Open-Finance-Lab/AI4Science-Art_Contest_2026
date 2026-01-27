# AI for Science and Art Task 2: Dataset & Baseline

We provide a curated dataset of Spin-Glass Ising model instances sourced from two Nature papers.

| Dataset       | Paper                                                                                                      | Original authors                                                                                                            | Our fork                   |
| ------------- | ---------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | -------------------------- |
| **DRL** | *Searching for spin glass ground states through deep reinforcement learning* (Fan Changjun et al., 2023) | [https://github.com/FFrankyy/DIRAC](https://github.com/FFrankyy/DIRAC)                                                         | `src/Task_2/dataset/DRL` |
| **VNA** | *Variational Neural Annealing* (Mohamed Hibat-Allah et al., 2021)                                        | [https://github.com/VectorInstitute/VariationalNeuralAnnealing](https://github.com/VectorInstitute/VariationalNeuralAnnealing) | `src/Task_2/dataset/VNA` |

## Dataset Composition

Our dataset is organized by the paper and exhbits the following features.

| Dataset | Dimension | Type of Ising Model | Instances |          Spins          |        Couplings        |      Coupling Strength      |
| ------- | --------- | ------------------- | :-------: | :---------------------: | :---------------------: | :-------------------------: |
| VNA     | 1D        | Classic             |    75    |  32 $\textbf{--}$ 128  |  31 $\textbf{--}$ 127  | 0.000 $\textbf{--}$ 1.000 |
|         | 2D        | Spin-Glass          |    75    | 100 $\textbf{--}$ 1600 | 180 $\textbf{--}$ 3120 | -1.000 $\textbf{--}$ 1.000 |
| DRL     | 2D        | Spin-Glass          |    75    | 400 $\textbf{--}$ 1225 | 800 $\textbf{--}$ 2450 | -4.088 $\textbf{--}$ 4.466 |
|         | 3D        | Spin-Glass          |    75    |  64 $\textbf{--}$ 512  | 192 $\textbf{--}$ 1536 | -3.850 $\textbf{--}$ 4.428 |

## Metric and Evaluation

We will be evaluating scores based on the Hamiltonian (shown below) of the solution obtained. Your goal: achieve the lowest energy configuration.
$$
H(\sigma) = - \sum_{i<j} J_{ij} \sigma_i \sigma_j
$$
Additionally we provide a baseline of scores from Gurobi, a commercial mixed-integer programming solver that employs a branch-cut algorithm to search for the ground state of Ising models. We encode the ground-state problem as a QUBO, solve it using Gurobi under an one-hour time limit, and report the resulting Hamiltonian. Baseline scores are located in `src/Task_2/dataset/baseline`. All baseline scores adhere to the following format:

```
The following baseline results are for 'VNA_100' instances from ID 1 to 25 :<Header>
-78.65040168401 :<Gurobi Result for ID 1>
-67.17205786930 :<Gurobi Result for ID 2>
-70.77779215906 :<Gurobi Result for ID 3>
-73.13928995860 :<Gurobi Result for ID 4>
-74.62129999245 :<Gurobi Result for ID 5>
-76.71913041124 :<Gurobi Result for ID 6>
-73.32729995254 :<Gurobi Result for ID 7>
-75.16187653078 :<Gurobi Result for ID 8>
...
-70.99738742294 :<Gurobi Result for ID 25>
```

## References

Fan, C., Shen, M., Nussinov, Z. et al. Searching for spin glass ground states through deep reinforcement learning. Nat Commun 14, 725 (2023). https://doi.org/10.1038/s41467-023-36363-w

Hibat-Allah, M., Inack, E.M., Wiersema, R. et al. Variational neural annealing. Nat Mach Intell 3, 952–961 (2021). https://doi.org/10.1038/s42256-021-00401-3

Gurobi Optimization, LLC. (Latest Release). Gurobi Optimizer Reference Manual. https://docs.gurobi.com/projects/optimizer/en/current/index.html

<p align="center">
<img src="https://cdn.jsdelivr.net/gh/QUANTUM-AND-ML/QBSA-DQAS@main/figures/Q&ML.png" alt="Q&ML Logo" width="600">
</p>

<h2><p align="center">A PyThon Library for Quantum Computation and Machine Learning</p></h2>
<h3><p align="center">Updated, Scalable, Easy Implement, Easy Reading and Comprehension</p></h3>


<p align="center">
    <a href="https://github.com/QUANTUM-AND-ML/Quantum-Kernel-Design/blob/main/LICENSE">
        <img alt="MIT License" src="https://img.shields.io/github/license/QUANTUM-AND-ML/Quantum-Kernel-Design">
    </a>
    <a href="https://www.python.org/downloads/release/python-3813/">
        <img alt="Version" src="https://img.shields.io/badge/Python-3.8-orange">
    </a>
    <a href="https://github.com/search?q=repo%3AQUANTUM-AND-ML%2FQuantum-Kernel-Design++language%3APython&type=code">
        <img alt="Language" src="https://img.shields.io/github/languages/top/QUANTUM-AND-ML/Quantum-Kernel-Design">
    </a>
   <a href="https://github.com/QUANTUM-AND-ML/Quantum-Kernel-Design/activity">
        <img alt="Activity" src="https://img.shields.io/github/last-commit/QUANTUM-AND-ML/Quantum-Kernel-Design">
    </a>
       <a href="https://www.nsfc.gov.cn/english/site_1/index.html">
        <img alt="Fund" src="https://img.shields.io/badge/supported%20by-NSFC-green">
    </a>
    <a href="https://twitter.com/FindOne0258">
        <img alt="twitter" src="https://img.shields.io/badge/twitter-chat-2eb67d.svg?logo=twitter">
    </a>


</p>
<br />



## Quantum & Machine Learning
Relevant scripts and data for the paper entitled "[**Quantum-Based Self-Attention Mechanism for Hardware-Aware Differentiable Quantum Architecture Search**](https://arxiv.org/abs/2512.02476)".

## Table of contents
* [**Main work**](#Main-work)
* [**Results display**](#Results-display)
* [**Python scripts**](#Python-scripts)
* [**Dependencies**](#Dependencies)

## Main work
The automated design of parameterized quantum circuits for variational algorithms in the NISQ era faces a fundamental limitation, as conventional differentiable architecture search relies on classical models that fail to adequately represent quantum gate interactions under hardware noise. We introduce the Quantum-Based Self-Attention for Differentiable Quantum Architecture Search (QBSA-DQAS), a meta-learning framework featuring quantum-based self-attention and hardware-aware multi-objective search. The framework employs a two-stage quantum self-attention module that computes contextual dependencies by mapping architectural parameters through parameterized quantum circuits, replacing classical similarity metrics with quantum-derived attention scores, then applies position-wise quantum transformations for feature enrichment. Architecture search is guided by a task-agnostic multi-objective function jointly optimizing noisy expressibility and Probability of Successful Trials (PST). A post-search optimization stage applies gate commutation, fusion, and elimination to reduce circuit complexity. Experimental validation demonstrates superior performance on VQE tasks and large-scale Wireless Sensor Networks. For VQE on H2, QBSA-DQAS achieves 0.9 accuracy compared to 0.89 for standard DQAS. Post-search optimization reduces discovered circuit complexity by up to 44% in gate count and 47% in depth without accuracy degradation. The framework maintains robust performance across three molecules and five IBM quantum hardware noise models. For WSN routing, discovered circuits achieve 8.6% energy reduction versus QAOA and 40.7% versus classical greedy methods, establishing the effectiveness of quantum-native architecture search for NISQ applications.

<p align="center">
<img src="https://cdn.jsdelivr.net/gh/QUANTUM-AND-ML/QBSA-DQAS@main/figures/figure_3a.png" alt="Figure 1" width="800">
</p>

**Figure 1.** An overview of hardware-aware quantum kernel design.

<p align="center">
<img src="https://cdn.jsdelivr.net/gh/QUANTUM-AND-ML/QBSA-DQAS@main/figures/figure_3b1.png" alt="Figure 2" width="650">
</p>

**Figure 2.** Subgraphs with $N=4,5,7$ and $8$ selected from the 133-qubit IBM Torino topology.

<p align="center">
<img src="https://cdn.jsdelivr.net/gh/QUANTUM-AND-ML/QBSA-DQAS@main/figures/figure_3d.png" alt="Figure 2" width="800">
</p>

**Figure 3.** The architectures of the GNN-1 and GNN-2.

## Results display


<p align="center">
<img src="https://cdn.jsdelivr.net/gh/QUANTUM-AND-ML/QBSA-DQAS@main/figures/figure_4c.png" alt="Figure 3" width="500">
</p>

**Figure 4.** Comparison of runtime of prediction and direct calculation for PST and KTA.

<p align="center">
<img src="https://cdn.jsdelivr.net/gh/QUANTUM-AND-ML/QBSA-DQAS@main/figures/figure_4e.png" alt="Figure 4" width="800">
</p>

**Figure 5.** Classification accuracy of different methods on the MNIST-5 classification task under noisy simulation.

## Python scripts
Here is the **brief introduction** to each python file for better understanding and usage:

* "Elivagar" folder contains benchmark code for Elivagar, QuantumNAS, Rondom, and other methods.
* "data" folder mainly contains various data files, such as example quantum circuits and partial datasets. Some datasets exceeding 25 MB could not be uploaded.
* "main.py" primarily includes dataset splitting and the **training** and **testing** of the neural network.
* "Dataset.py" mainly implements the construction of training datasets for PST and KTA.
* "GNN_generate_datas.py" mainly implements the generation of random quantum circuits used for training **Graph Neural Networks** (*GNNs*) to compute the ground-state energy of hydrogen molecules.
* "circuits_generation.py" mainly contains functions for the random generation of quantum circuits.
* "circuit_to_graph.py" primarily defines a class that allows **the conversion of quantum circuits into graphs**.
* "KTA_calculate_for_two_objective_classification.py" and "KTA_calculate_for_multi_objective_classification.py" respectively contain functions for **computing KTA** in binary and multi-class classification tasks.
* "PST_calculation_qiskit.py" mainly defines functions for calculating probability of successful trials (PST) values of quantum circuits.
* "GAT.py" contains the architectures of the constructed **Graph Neural Networks** (*GNNs*).
* "MNIST_generate.py" and "MNIST_mRMR.py" are demonstration programs for data selection and dimensionality reduction on the MNIST dataset, respectively.

## Dependencies
- 3.10 >= Python >= 3.7
- PyTorch >= 2.0.1
- Qiskit >= 0.36.1
- PennyLane >= 0.30.0
- Parallel computing may require NVIDIA GPUs acceleration


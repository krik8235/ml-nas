# Neural Architecture Search (NAS)

An exploration of primary search strategies for Neural Architecture Search and its practical applications.

## Introduction to NAS

Designing neural network architectures by hand is a resource-intensive task that requires significant human expertise. Neural Architecture Search (NAS) automates this process by treating network design as an optimization problem. A NAS algorithm explores a vast range of potential architectures and evaluates each one to find the most effective design.

The core process of NAS involves three main steps:

- Define a Search Space: Establish the set of all possible network architectures the algorithm can construct.

- Select a Search Strategy: Choose an algorithm to navigate the search space (e.g., Reinforcement Learning, Evolutionary Algorithms).

- Evaluate Performance: Assess the validation performance of the chosen architecture to find the optimal design that minimizes losses.


## Common Search Strategies

This repository demonstrates three common NAS search strategies:

1. Reinforcement Learning (RL)

Approach: An "agent" (a neural network) is trained to sequentially choose the components of an architecture, receiving a "reward" based on the architecture's performance. The agent learns to make choices that maximize this cumulative reward.
Best For: Complex search spaces and multi-objective optimization where you need to balance factors like accuracy, latency, and model size.

2. Evolutionary Algorithms (EAs)

Approach: Inspired by natural selection, EAs maintain a population of network architectures. High-performing architectures ("elites") are selected to "mutate" and "crossover" to create new offspring, evolving the population over generations to find better designs.
Best For: Extremely broad search spaces, as EAs are less likely to get stuck in local optima, and when you can run evaluations in parallel.

3. Gradient-based Methods

Approach: These methods use a "one-shot" supernetwork that contains all possible operations. The search is framed as a continuous optimization problem, and the architecture is optimized using gradient descent on this supernetwork.
Best For: Situations where computational efficiency is critical, and for single-objective optimization tasks.


Other methods like Bayesian Optimization and Grid/Random Search are also popular.


## Simulation and Results
This project includes a simulation comparing the three search strategies on a simple Recurrent Neural Network (RNN) task.

| Strategy  | Best Validation MSE | Key Finding     | 
|------------|---------------------| ------------- |
| Evolutionary Algorithms | 0.1498   | Achieved the lowest validation loss, demonstrating its effectiveness in exploring the search space.  |
| Reinforcement Learning  | 0.2744   | Found a competitive architecture, though its performance varied significantly between episodes.    |
| Gradient-based Methods  | 3.6725   | Performed the worst in this simulation, highlighting its potential limitations with certain search spaces. | 


## Conclusion

NAS is a powerful tool for discovering novel, high-performing architectures that can outperform human-designed models. While traditional methods have faced challenges with high computational costs and a lack of generalization, the field is continuously evolving with more efficient algorithms.

<hr>

Author: Kuriko IWAI

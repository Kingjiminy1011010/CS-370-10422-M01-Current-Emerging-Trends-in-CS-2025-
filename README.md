# CS-370-10422-M01-Current-Emerging-Trends-in-CS-2025-

Pirate Intelligent Agent: Deep Q-Learning Pathfinding

Project Overview

This project implements a Deep Q-Learning (DQL) intelligent agent designed to solve a pathfinding problem within a simulated $8 \times 8$ maze. The agent, acting as a pirate, learns the optimal sequence of moves to find a hidden treasure while avoiding obstacles. This notebook serves as a practical demonstration of applying reinforcement learning (RL) and neural networks to solve dynamic problems in a game environment.

1. Project Work Explained

Code Provided

The starter codebase established the environment and core utilities necessary for training:

TreasureMaze.py: Defined the $8 \times 8$ maze environment, including the state space, obstacle locations, and the reward function (e.g., $+1$ for the treasure, large penalties for walls/out-of-bounds movement).

GameExperience.py: Implemented the experience replay memory to store and sample past transitions (state, action, reward, next state) for batch training.

build_model function: Provided the architecture for the Deep Q-Network (DQN). This Keras sequential model included an input layer of 64 units, two dense hidden layers with PReLU activation for non-linear learning, and an output layer of 4 units (one for each action), compiled with the Adam optimizer.

play_game and completion_check functions: Utilities for running and evaluating the trained agent's performance.

Code Created (Completed)

My work focused on completing the training logic within the qtrain function, which is the core DQL algorithm implementation:

Q-Training Loop: I implemented the primary training loop, which manages the episodes (games) and the interaction between the agent and the environment.

$\epsilon$-Greedy Policy: Implemented the logic for balancing exploitation (using the model's prediction) and exploration (taking a random action) based on the current $\epsilon$ value.

Experience Replay Integration: Ensured that the agent's experiences were properly stored in the memory buffer and that random batches were sampled to calculate targets for network training.

Reward Maximization: Used the Bellman equation principle to update the network weights by minimizing the Mean Squared Error (MSE) between the predicted Q-values and the calculated target Q-values, ultimately guiding the agent toward the path that maximizes its cumulative reward.

Convergence Condition: Configured the training to continue until the agent achieved a $100\%$ win rate over a specified history window and successfully passed the completion_check from all valid starting positions.

2. Connecting Learning to Computer Science

What Computer Scientists Do and Why It Matters

Computer scientists are not just programmers; they are problem solvers who use computational thinking to design algorithms, develop software, and create intelligent systems across every industry. This project demonstrates core computer science work: framing a real-world problem (pathfinding) as a computational challenge (a Markov Decision Process), selecting an appropriate algorithm (DQL), and designing, implementing, and debugging the solution. This matters because computational solutions are fundamental to modern life, powering everything from logistics and finance to medicine and, in this case, game AI.

How I Approach a Problem as a Computer Scientist

My approach to solving this pathfinding problem followed a standard scientific methodology:

Decomposition and Modeling: The problem was decomposed into its core components: the agent, the environment (the maze), the state representation (the $8 \times 8$ flattened vector), and the objective (maximizing reward). The problem was modeled as a Reinforcement Learning task.

Algorithm Selection: Given the continuous learning requirement and the desire for generalization, Deep Q-Learning was chosen over a simple search algorithm (like BFS or A*) or a traditional Q-table.

Implementation and Iteration: The DQL logic was implemented, integrating the neural network with the RL loop. Iterative testing and tuning of hyperparameters like the epsilon decay rate, memory size, and epochs were necessary to achieve optimal convergence (the $100\%$ win rate).

Ethical Responsibilities

In designing intelligent agents, several ethical responsibilities come into play, even for a simple game NPC:

Bias and Fairness (General AI): Although minimal here, in real-world scenarios, agents must be trained on diverse data to prevent biased outcomes that disadvantage specific user groups.

Transparency and Explainability: Users and stakeholders have a right to understand why an AI makes the decisions it does. For our pirate, the action is transparent (it follows the highest Q-value), but for complex systems, we must ensure the decision-making process is auditable.

User Experience and Intent: The agent's behavior must align with its intended role. Here, the pirate is meant to be a challenging NPC, enhancing the game. Our responsibility is to ensure the agent's complexity serves the end-user's experience without exploiting flaws or frustrating players unintentionally.

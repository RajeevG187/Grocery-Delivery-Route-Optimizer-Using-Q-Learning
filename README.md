---

# Grocery Delivery Route Optimizer Using Q-Learning

This repository contains Python code implementing a reinforcement learning approach for optimizing grocery delivery routes. The code utilizes Q-learning to learn the best sequence of actions (delivery stops) to minimize the total cost and distance traveled while ensuring efficient delivery of groceries.

## Table of Contents

- [Overview](#overview)
- [Dependencies](#dependencies)
- [Usage](#usage)
- [File Description](#file-description)
- [Functions](#functions)
- [License](#license)

## Overview

The code simulates a scenario where a delivery person needs to optimize the route for delivering groceries to various locations. The goal is to learn the optimal sequence of actions (delivery stops) to minimize both the distance traveled and the overall delivery cost.

Key components of the code include:
- Representation of delivery locations and items.
- Calculation of distances between delivery locations.
- Definition of a state space representing all possible delivery states.
- Implementation of Q-learning algorithm to learn the optimal delivery route.
- Evaluation of learned policy against a random delivery route.

## Dependencies

The following Python libraries are required to run the code:
- NumPy
- Matplotlib
- Math
- Itertools
- Copy
- Random
- Sys

You can install these dependencies using pip:

```bash
pip install numpy matplotlib
```

No additional installation is needed for the standard libraries such as Math, Itertools, Copy, Random, and Sys as they are part of the Python standard library and come pre-installed with most Python distributions.

## Usage

1. Clone this repository to your local machine:

```bash
git clone https://github.com/RajeevG187/Grocery-Delivery-Route-Optimizer-Using-Q-Learning.git
```

2. Navigate to the directory containing the code:

```bash
cd Grocery-Delivery-Route-Optimizer-Using-Q-Learning
```

3. Run the main Python script:

```bash
python Grocery Delivery Route Optimizer Using Q-Learning.ipynb
```

4. Follow the on-screen instructions to observe the learning process and evaluate the learned policy.

## File Description

- `grocery_delivery_optimizer.py`: Main Python script implementing the Q-learning algorithm for optimizing grocery delivery routes.
- `README.md`: This README file providing an overview of the project and instructions for usage.
- `LICENSE`: License file specifying the terms under which the code is distributed.

## Functions

### `haversine_distance(loc1, loc2)`
- Calculates the Haversine distance between two locations.
- Inputs:
  - `loc1`: A `Location` object representing the first location.
  - `loc2`: A `Location` object representing the second location.
- Returns:
  - `distance`: The distance between `loc1` and `loc2` in kilometers.

### `reward(current_state, next_state, distance)`
- Computes the reward for transitioning from the current state to the next state.
- Inputs:
  - `current_state`: The current state, represented as a `State` object.
  - `next_state`: The next state, represented as a `State` object.
  - `distance`: The distance between the current and next locations.
- Returns:
  - `reward`: The reward for the transition.

### `distance_penalty(current_state, next_state, distance)`
- Computes the penalty based on the distance traveled in the transition.
- Inputs:
  - `current_state`: The current state, represented as a `State` object.
  - `next_state`: The next state, represented as a `State` object.
  - `distance`: The distance between the current and next locations.
- Returns:
  - `penalty`: The penalty based on the distance traveled.

### `availability_in_shop(current_state, next_state)`
- Computes the probability of item availability in the next shop.
- Inputs:
  - `current_state`: The current state, represented as a `State` object.
  - `next_state`: The next state, represented as a `State` object.
- Returns:
  - `probability`: The probability of item availability.

### `M(current_shop, next_shop)`
- Computes a metric for the transition probability between two shops.
- Inputs:
  - `current_shop`: The index of the current shop.
  - `next_shop`: The index of the next shop.
- Returns:
  - `metric`: The transition probability metric.

### `takeaction(current_state, action)`
- Selects the next state based on the current state and action taken.
- Inputs:
  - `current_state`: The current state, represented as a `State` object.
  - `action`: The action taken (index of the next shop).
- Returns:
  - `next_state`: The next state, represented as a `State` object.
  - `reward`: The reward for the transition.

### `e_greedy(epsilon, Q_s)`
- Implements an epsilon-greedy strategy for action selection.
- Inputs:
  - `epsilon`: The exploration rate.
  - `Q_s`: The Q-values for the current state.
- Returns:
  - `action`: The selected action.

### `q_learning(no_episodes, no_steps, alpha, gamma, epsilon)`
- Performs Q-learning to learn the optimal delivery route.
- Inputs:
  - `no_episodes`: The number of episodes for training.
  - `no_steps`: The maximum number of steps per episode.
  - `alpha`: The learning rate.
  - `gamma`: The discount factor.
  - `epsilon`: The exploration rate.
- Returns:
  - `Q`: The learned Q-values.
  - `Rewards`: The rewards obtained in each episode.
  - `avg_rewards`: The average rewards over episodes.

## License

This project is licensed under © Rajeev Goel (12241460), Vedant Marodkar (12240990), IIT Bhilai.

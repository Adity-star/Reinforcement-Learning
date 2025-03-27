# Lunar Lander Reinforcement Learning Agent with Stable-Baselines3 PPO

---

## Introduction

This project implements a reinforcement learning agent that learns to land on the Moon 🌕 in the **Lunar Lander** environment using **Stable-Baselines3's Proximal Policy Optimization (PPO)** algorithm. The agent is trained to safely land the spacecraft on a flat surface, maximizing its reward while minimizing fuel consumption and avoiding crashes.

PPO is a state-of-the-art policy gradient algorithm that strikes a balance between performance and computational efficiency, making it an ideal choice for continuous control tasks like Lunar Lander.

---

## Problem Overview

The **Lunar Lander** environment, part of the OpenAI Gym toolkit, involves a spacecraft that needs to land safely on the Moon. The agent must control the lander's movements and adjust its velocity, angle, and fuel usage to land on a flat surface.

### Environment Specifications:
- **State space**: The state is an 8-dimensional vector, which includes:
  - Lander's position, velocity, angle, and angular velocity.
- **Action space**: The agent can choose from 4 discrete actions:
  1. Do nothing
  2. Fire main engine
  3. Fire left engine
  4. Fire right engine
- **Goal**: The agent needs to land the spacecraft safely without crashing and while using the least amount of fuel.

---

## Agent Architecture

The agent is trained using **Proximal Policy Optimization (PPO)** from **Stable-Baselines3**, a modern reinforcement learning algorithm designed to ensure stability and efficiency during training.

### Key Features of PPO:
1. **Policy Gradient**: PPO directly optimizes the policy by updating it in small, safe steps.
2. **Clipped Objective**: PPO introduces a clipped objective to ensure that the policy doesn't change too drastically between updates, improving stability.
3. **Advantage Estimation**: PPO uses a mechanism called Generalized Advantage Estimation (GAE) to reduce variance in the gradient estimates, making training more efficient.

The agent uses a neural network to represent the policy, which is continuously updated during training.

---

## Training Process

The agent is trained using **Stable-Baselines3's PPO** algorithm, with the following training components:

1. **Exploration vs. Exploitation**: The agent initially explores the environment randomly, then gradually exploits its learned policy as it gains more experience.
2. **Advantage Function**: PPO uses the **advantage function** to guide the agent's decision-making process by estimating how good a particular action is compared to the average action in a given state.
3. **Training Loop**: The agent interacts with the environment, stores experiences in a replay buffer, and updates its policy based on the rewards and advantages received during each step.

Training proceeds over multiple episodes where the agent interacts with the Lunar Lander environment, continually refining its policy to maximize rewards.

---

## Results

The agent progressively learns to land the Lunar Lander with increasing precision and efficiency. The following are key metrics after training:

- **Average Reward**: The agent's average reward steadily improves as it learns to land more successfully.
- **Fuel Efficiency**: The agent learns to minimize fuel consumption while maintaining control of the lander.
- **Landing Success Rate**: The agent's success rate in landing safely increases over time as its policy improves.

---

## Preview Video

Watch the Lunar Lander agent in action as it learns to land on the Moon 🌕! The video below demonstrates how the agent improves over time:

[![Lunar Lander Agent Preview](https://via.placeholder.com/600x300)](https://huggingface.co/sb3/ppo-LunarLander-v2/resolve/main/replay.mp4)



---



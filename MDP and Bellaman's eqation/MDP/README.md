# Understanding Markov Decision Process (MDP) in Reinforcement Learning

The **Markov Decision Process (MDP)** is a mathematical framework used to describe an environment in Reinforcement Learning (RL). It provides a formal way to model decision-making where an agent interacts with an environment to achieve a goal. In this guide, we’ll break down the key components of an MDP and explain how they relate to RL.

## Table of Contents
1. [What is MDP?](#what-is-mdp)
2. [Key Components of an MDP](#key-components-of-an-mdp)
   - [States](#states)
   - [Actions](#actions)
   - [Transition Model](#transition-model)
   - [Rewards](#rewards)
   - [Policy](#policy)
3. [How Does MDP Work in RL?](#how-does-mdp-work-in-rl)
4. [MDP Example](#mdp-example)
5. [Mathematical Representation](#mathematical-representation)
6. [Applications of MDP in RL](#applications-of-mdp-in-rl)
7. [Conclusion](#conclusion)
8. [Summary](#summary)
9. [Additional Resources](#additional-resources)

---

## What is MDP?

A **Markov Decision Process (MDP)** is a decision-making framework that describes an environment in which an agent makes decisions. It provides the structure for RL problems where the agent’s goal is to maximize some notion of cumulative reward over time.

An MDP consists of the following components:
- A set of **states** describing the environment.
- A set of **actions** available to the agent.
- A **transition model** that describes how the agent's actions affect the environment.
- A **reward function** that gives feedback to the agent after taking an action.
- A **policy** that defines the agent’s strategy for choosing actions.

The fundamental assumption of an MDP is that it follows the **Markov property**: the future state depends only on the current state and action, not on the history of previous states.

[Back to Table of Contents](#table-of-contents)

---

## Key Components of an MDP

### States

- **Definition**: A **state** represents a configuration or situation of the environment at a specific point in time.
- **Example**: In a grid world, a state might represent the position of the agent on the grid.
- **Importance in RL**: The state provides the information the agent uses to make decisions.

### Actions

- **Definition**: An **action** is a decision made by the agent that affects the environment and transitions it from one state to another.
- **Example**: In a grid world, actions might include moving up, down, left, or right.
- **Importance in RL**: The agent chooses actions based on its policy to maximize rewards.

### Transition Model

- **Definition**: The **transition model** describes the probability of moving from one state to another given a specific action. It represents the dynamics of the environment.
- **Notation**: Denoted as \( P(s' | s, a) \), which is the probability of transitioning to state \( s' \) from state \( s \) when action \( a \) is taken.
- **Example**: In a grid world, if the agent moves up, the transition model defines the likelihood of reaching the next state above the current position.

### Rewards

- **Definition**: A **reward** is a scalar value the agent receives after taking an action in a state. It provides feedback on the quality of the agent's action.
- **Example**: In a maze-solving task, the agent might get a positive reward for reaching the goal and a negative reward for bumping into a wall.
- **Importance in RL**: The reward function guides the agent to learn which actions lead to higher cumulative rewards.

### Policy

- **Definition**: A **policy** is a strategy that defines how an agent should behave. It maps from states to actions, telling the agent which action to take in each state.
- **Notation**: Denoted as \( \pi(s) \), which represents the action chosen by the agent when in state \( s \).
- **Example**: A simple policy might be: “Always move up if possible; otherwise, move right.”

[Back to Table of Contents](#table-of-contents)

---

## How Does MDP Work in RL?

In reinforcement learning, an agent interacts with an environment and learns how to make decisions based on the feedback it gets. The MDP framework helps define this interaction. Here's how the agent typically operates within an MDP:

1. **Initialization**: The agent starts in an initial state \( s_0 \).
2. **Decision-making**: The agent chooses an action \( a_t \) based on its policy \( \pi(s_t) \) in the current state \( s_t \).
3. **Environment Feedback**: The agent takes action \( a_t \), and the environment responds by transitioning to a new state \( s_{t+1} \) according to the transition model \( P(s' | s, a) \).
4. **Reward**: The agent receives a reward \( r_t \) from the environment based on the action taken.
5. **Repeat**: The agent continues to make decisions, receive feedback, and adjust its policy based on the rewards it receives.

Over time, the agent's goal is to learn an optimal policy that maximizes the expected sum of rewards.

[Back to Table of Contents](#table-of-contents)

---

## MDP Example

Imagine an agent in a simple grid world:
- **States**: The positions on the grid (e.g., (0, 0), (1, 1)).
- **Actions**: Move up, move down, move left, move right.
- **Transition Model**: If the agent moves right, it will transition to the state to the right of its current position.
- **Rewards**: The agent receives a reward of +1 for reaching the goal and a reward of -1 for hitting a wall.
- **Policy**: The agent’s policy might be to always move towards the goal while avoiding walls.

### Illustration:
[ S ] - Start [ ] - Empty space [ G ] - Goal [ W ] - Wall

In this example, the agent’s task is to reach the goal from the start while avoiding the walls.

## Mathematical Representation

MDPs can be represented mathematically using the following components:
- **State Space**: \( S = \{ s_1, s_2, \dots, s_n \} \)
- **Action Space**: \( A = \{ a_1, a_2, \dots, a_m \} \)
- **Transition Function**: \( P(s' | s, a) \) – Probability of transitioning to state \( s' \) after taking action \( a \) from state \( s \)
- **Reward Function**: \( R(s, a) \) – Reward received after taking action \( a \) in state \( s \)
- **Discount Factor**: \( \gamma \) – Factor that discounts future rewards, where \( 0 \leq \gamma \leq 1 \)
- **Policy**: \( \pi(s) \) – The strategy that defines the action to take in state \( s \)

The agent aims to maximize the **expected cumulative reward** over time, which is typically represented as:

\[
\mathbb{E} \left[ \sum_{t=0}^{T} \gamma^t R(s_t, a_t) \right]
\]

Where \( \gamma \) is the discount factor, which determines the weight given to future rewards.

[Back to Table of Contents](#table-of-contents)

---

## Applications of MDP in RL

MDPs are used in many RL applications, such as:
- **Robotics**: Teaching robots to navigate environments, pick up objects, or perform tasks.
- **Game AI**: Training agents to play games by learning strategies through trial and error.
- **Autonomous Vehicles**: Teaching self-driving cars to make decisions based on traffic and road conditions.
- **Healthcare**: Modeling patient treatment strategies to maximize health outcomes over time.

---

## Conclusion

The Markov Decision Process (MDP) provides a solid foundation for understanding how reinforcement learning works. By breaking down the environment into states, actions, rewards, and transitions, MDP helps model decision-making problems in a formalized way. Whether you’re building a simple agent to play a game or a complex robotic system, MDPs are essential for creating intelligent agents capable of making effective decisions.

[Back to Table of Contents](#table-of-contents)

---

## Summary
- Agent & Environment Interface: At each step t the agent receives a state S_t, performs an action A_t and receives a reward R_{t+1}. The action is chosen according to a policy function pi.
- The total return G_t is the sum of all rewards starting from time t . Future rewards are discounted at a discount rate gamma^k.
- Markov property: The environment's response at time t+1 depends only on the state and action representations at time t. The future is independent of the past given the present. Even if an environment doesn't fully satisfy the Markov property we still treat it as if it is and try to construct the state representation to be approximately Markov.
- Markov Decision Process (MDP): Defined by a state set S, action set A and one-step dynamics p(s',r | s,a). If we have complete knowledge of the environment we know the transition dynamic. In practice, we often don't know the full MDP (but we know that it's some MDP).
- The Value Function v(s) estimates how "good" it is for an agent to be in a particular state. More formally, it's the expected return G_t given that the agent is in state s. v(s) = Ex[G_t | S_t = s]. Note that the value function is specific to a given policy pi.
- Action Value function: q(s, a) estimates how "good" it is for an agent to be in states and take action a. Similar to the value function, but also considers the action.

## Additional Resources

- [Reinforcement Learning: An Introduction](http://incompleteideas.net/book/the-book-2nd.html) by Richard S. Sutton and Andrew G. Barto (book)

Feel free to reach out with questions or contributions!

[Back to Top](#table-of-contents)


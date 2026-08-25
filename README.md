# SARSA Learning Algorithm

## AIM
To implement the on-policy SARSA (State-Action-Reward-State-Action) learning algorithm and use it to learn an optimal policy and action-value function for the FrozenLake-v1 environment.

## PROBLEM STATEMENT
In the FrozenLake environment, an agent must learn how to move from a starting state to a goal state on a grid. Some grid cells are frozen and safe, while others are holes that terminate an episode with no reward. The agent initially does not know the transition dynamics or which actions lead to the goal. Using trial-and-error interaction with the environment, it must estimate the value of each state-action pair and discover a policy that reaches the goal reliably. The learned SARSA policy is evaluated using its state-value function, action-value function, success rate, average return, regret, and comparison with the optimal values obtained through value iteration.

## SARSA LEARNING ALGORITHM
SARSA is an on-policy temporal-difference control algorithm. It updates the value of the action actually selected by the current policy.

1. Initialize the action-value table $Q(s,a)$ to zero for every state-action pair.
2. Initialize the learning rate $\alpha$ and exploration rate $\epsilon$ schedules.
3. For each episode, reset the environment and observe the initial state $S$.
4. Select an action $A$ from $S$ using an epsilon-greedy policy: choose a random action with probability $\epsilon$; otherwise choose the action with the highest $Q(S,a)$ value.
5. Execute $A$, then observe the reward $R$, the next state $S'$, and whether the episode has terminated.
6. If the episode has terminated, set the target to $R$. Otherwise, select the next action $A'$ using the same epsilon-greedy policy and set the target to $R + \gamma Q(S',A')$.
7. Update the current action value using
   $$Q(S,A) \leftarrow Q(S,A) + \alpha\left[\text{target} - Q(S,A)\right].$$
8. If the episode has not terminated, set $S \leftarrow S'$ and $A \leftarrow A'$, then repeat from Step 5.
9. Decay $\alpha$ and $\epsilon$ according to their schedules while maintaining their minimum values.
10. After training, derive the policy by selecting the action with the largest learned $Q(s,a)$ value in each state and evaluate its performance.

## SARSA LEARNING FUNCTION
### Name:
### Register Number:

Include the SARSA Learning function.

## OUTPUT
Mention the optimal policy, optimal value function, and success rate for the optimal policy. Include a plot comparing the state-value functions of the Monte Carlo method and SARSA learning.

## RESULT
SARSA learns an action-value function and an on-policy strategy for reaching the goal in FrozenLake. Compare the learned policy's success rate and value function with the optimal results after executing the notebook.

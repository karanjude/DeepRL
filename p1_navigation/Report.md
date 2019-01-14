### Description

In a unity ML-Agent environment, yellow and blue bananas are failling. Here i train a DQN agent to capture falling yellow bananas. A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana.

#### Actions

```
At each time step, the agent has four actions at its disposal:

* 0 - walk forward
* 1 - walk backward
* 2 - turn left
* 3 - turn right
```

#### State

```
The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of 
objects around agent's forward direction. 

Number of actions: 4
States look like: [1.         0.         0.         0.         0.84408134 0.
 0.         1.         0.         0.0748472  0.         1.
 0.         0.         0.25755    1.         0.         0.
 0.         0.74177343 0.         1.         0.         0.
 0.25854847 0.         0.         1.         0.         0.09355672
 0.         1.         0.         0.         0.31969345 0.
 0.        ]
States have length: 37
```

#### Success Criteria 

```The agent should be able to receive an average reward (over 100 episodes) of at least +13```


### Learning Algorithm 

DQN - Deep Q-Learning algorithm represents the optimal action-value function q* as a neural network instead of a table.

Note:

```
θ_target = τ*θ_local + (1 - τ)*θ_target
```

target network is updated using a local q network. This helps in fixing the targets and making the update more stable.

#### Hyper parameters

1. eps_start (float): starting value of epsilon, for epsilon-greedy action selection by the agent. Value: eps_start=1.0
2. eps_end (float): minimum value of epsilon. Value: eps_decay=0.995.
3. eps_decay (float): multiplicative factor (per episode) for decreasing epsilon. Value: eps_decay=0.995
4. GAMMA = 0.99            # discount factor
5. TAU = 1e-3              # for soft update of target parameters
6. LR = 5e-4               # learning rate 

#### Model architecture

```
QNetwork(
  (fc1): Linear(in_features=37, out_features=64, bias=True)
  (fc2): Linear(in_features=64, out_features=64, bias=True)
  (fc3): Linear(in_features=64, out_features=4, bias=True)
)
```

The network consists of 3 fully connected layers. Input layer takes in a state vector. Final layer produces 
3 action values. The layers themselves are connected via relu activation units units. The final action value is selected via an arg max.

### Plot of rewards

![Reward plot](https://github.com/karanjude/DeepRL/blob/master/p1_navigation/reward_plot.png "Reward Plot")

#### Episodes needed to solve the environment

The agent needs to train for atleast 600 episodes to get a score of > 13.

### Ideas for future work

#### Double DQN
Deep Q-Learning tends to overestimate action values. Double Q-Learning has been shown to work well in practice to help with this. Intead of using a plain DQN network, a Double DQN network can be used.

#### Prioritized Experience Replay
Deep Q-Learning samples experience transitions uniformly from a replay memory. Prioritized experienced replay is based on the idea that the agent can learn more effectively from some transitions than from others, and the more important transitions should be sampled with higher probability.

#### Dueling DQN
Currently, in order to determine which states are (or are not) valuable, we have to estimate the corresponding action values for each action. However, by replacing the traditional Deep Q-Network (DQN) architecture with a dueling architecture, we can assess the value of each state, without having to learn the effect of each action.

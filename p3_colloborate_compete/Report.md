### Project 
This project uses multi DDPG agent, to learn an agent in continuous space. I train N (2) agents parallely as they converge faster and the overall agent performance also improves. Here a global actor and critic is trained on data received from all the agents. 

Note: this is not the same as a multi agent training where critic within an agent is trained on global data and actor wihtin an agent is trained on agent specific local data. For this project, one actor/critic trained on global data from all N agent seem to work. This might not be true for more complex environments. 

### Model

I use an actor critic DDPG agent. The model consists of an actor and a critic having the following architecture.

```
Actor(
  (fc1): Linear(in_features=33, out_features=256, bias=True)
  (fc2): Linear(in_features=256, out_features=128, bias=True)
  (fc3): Linear(in_features=128, out_features=4, bias=True)
)

Critic(
  (fcs1): Linear(in_features=33, out_features=256, bias=True)
  (fc2): Linear(in_features=260, out_features=128, bias=True)
  (fc3): Linear(in_features=128, out_features=1, bias=True)
)
```

### Hyper parameters, The following hyper parameters were used for the agent:

```
BUFFER_SIZE = int(1e5)    # replay buffer size
BATCH_SIZE = 128          # minibatch size
GAMMA = 0.99              # discount factor
TAU = 1e-3                # for soft update of target parameters
ACTOR_LR = 1e-4           # learning rate of actor 
CRITIC_LR = 1e-4          # learning rate of critic
ACTOR_WEIGHT_DECAY = 0.0  # L2 weight decay of actor
CRITIC_WEIGHT_DECAY = 0.0 # L2 weight decay of critic
```
### Plot of rewards during training

![Reward plot](https://github.com/karanjude/DeepRL/blob/master/p3_colloborate_compete/training_reward_plot.png "Training Reward Plot")

### Episodes needed to solve the environment

It took the agent 1000 episodes for the model to consistently get an average score of .5+. 

### Ideas for future work

- ![Multi Agent] (https://papers.nips.cc/paper/7217-multi-agent-actor-critic-for-mixed-cooperative-competitive-environments.pdf "Multi Agent Actor Critic for Mixed Cooperative Competitive environments"). It can help with stability and convergence, in a non stationary environment.

- ![Priortized Experience Replay] (https://arxiv.org/abs/1511.05952 "Priortized Experience Replay") Prioritized Experience Replay which helps with important but less frequently seen experiences

It might be possible to use PPO, A3C, D4PG (Distributed Distributional Deterministic Policy Gradients) to train the model quicker.

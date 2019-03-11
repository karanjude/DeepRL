### Project 
This project uses DDPG, to learn an agent in continuous space. Infact, during the project realized it better to train N agents parallely as they converge faster and the overall agent performance also improves.

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

![Reward plot](https://github.com/karanjude/DeepRL/blob/master/p2_continuous_control/training_reward_plot.png "Training Reward Plot")

### Plot of rewards during inference

![Reward plot](https://github.com/karanjude/DeepRL/blob/master/p2_continuous_control/reward_plot.png "Reward Plot")

### Episodes needed to solve the environment

It took the agent 191 episodes for the model to consistently get an average score of 30+. For inference, model got an average score of 30+. 

### Ideas for future work

- https://arxiv.org/abs/1511.05952 - "Priortized Experience Replay". Prioritized Experience Replay which helps with important but less frequently seen experiences

- Training the agent with PPO (Proximal Policy Optimization). 

- Batch Prop a drouputs could help with faster training. 

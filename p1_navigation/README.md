
#### Project Details
Train an agent to capture falling bananas. 

The simulation contains a single agent that navigates a large environment. At each time step, it has four actions at its disposal:

* 0 - walk forward
* 1 - walk backward
* 2 - turn left
* 3 - turn right

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction. A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana.

```
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

#### Trained agent video
Video of a trained DQN agent to capture bananas - https://youtu.be/6mM8IUraksc

#### Project Files
* Files for Navigation project can be found at https://github.com/karanjude/DeepRL/tree/master/p1_navigation

* Agent code that implements DQN can be found at https://github.com/karanjude/DeepRL/blob/master/p1_navigation/dqn_agent.py

* DQN uses a QNetwork that be found at https://github.com/karanjude/DeepRL/blob/master/p1_navigation/model.py 

* Saved QNetwork Weights - https://github.com/karanjude/DeepRL/blob/master/p1_navigation/checkpoint.pth


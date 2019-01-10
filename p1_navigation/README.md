
### Project Details
In a unity ML-Agent environment, yellow and blue bananas are failling. Train an agent to capture falling yellow bananas. A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana.

1. Actions

```
At each time step, the agent has four actions at its disposal:

* 0 - walk forward
* 1 - walk backward
* 2 - turn left
* 3 - turn right
```

2. State

```
The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction. 

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

3. Success Criteria 

```The agent should be able to receive an average reward (over 100 episodes) of at least +13```

### Getting Started

To set up your python environment to run the code in this repository, follow the instructions below.

1. Create (and activate) a new environment with Python 3.6.

	- __Mac__: 
	```bash
	conda create --name drlnd python=3.6
	source activate drlnd
	```
	
2. Clone the DRLND repository (if you haven't already!), and navigate to the `python/` folder.  Then, install several dependencies.
```bash
git clone https://github.com/udacity/deep-reinforcement-learning.git
cd deep-reinforcement-learning/python
pip install .
```

3. Clone this repository 
```bash
git clone https://github.com/karanjude/DeepRL.git
cd DeepRL/p1_navigation
```

4. Download Unity ML agent env from https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip
and unzip place it under DeepRL/p1_navigation

5. Start jupyter and open Navigation.ipynb
```bash
jupyter notebook
```

### Trained agent video
Video of a trained DQN agent to capture bananas - https://youtu.be/6mM8IUraksc

### Project Files
* Files for Navigation project can be found at https://github.com/karanjude/DeepRL/tree/master/p1_navigation

* Agent code that implements DQN can be found at https://github.com/karanjude/DeepRL/blob/master/p1_navigation/dqn_agent.py

* DQN uses a QNetwork that be found at https://github.com/karanjude/DeepRL/blob/master/p1_navigation/model.py 

* Saved QNetwork Weights - https://github.com/karanjude/DeepRL/blob/master/p1_navigation/checkpoint.pth


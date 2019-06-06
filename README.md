[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/42135623-e770e354-7d12-11e8-998d-29fc74429ca2.gif "Trained Agent"
[image2]: https://user-images.githubusercontent.com/10624937/42135622-e55fb586-7d12-11e8-8a54-3c31da15a90a.gif "Soccer"


# Project 3: Collaboration and Competition

### Introduction

For this project, the work will be with the [Tennis](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#tennis) environment.

![Trained Agent][image1]


In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1.  If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01.  Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation.  Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping. 

Expected Mean Reward: +0.5

### Solving the Environment

This project uses a Unity environment that contains two agents control rackets. The task is episodic, and in order to solve the environment, the agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents). Specifically,

- After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores.
- This yields a single **score** for each episode.

The environment is considered solved, when the average (over 100 episodes) of those **scores** is at least +0.5.

```python
env = UnityEnvironment(file_name='Tennis.exe')
```
### Instructions
This project runs locally in CPU on Windows 10 environment. Here are the steps to setup the environment:
1. Create (and activate) a new environment with Python 3.6.
	```
	- __Windows__: 
	```bash
	conda create --name drlnd python=3.6 
	activate drlnd
	```

2. Install these dependencies in the environment on windows 10
	- __Install Unity ML-Agents__
	```bash
	pip3 install --user mlagents
	```	
	- __Install Unity Agents__
	```bash
	pip install unityagents
	```	
	- __Install Pytorch__
	```bash
	conda install pytorch torchvision cudatoolkit=9.0 -c pytorch
	```
3. Download the `p3_collab-compet` environment from one of the links below and select the environment that matches your Windows operating system:
    -Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
    -Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)
 
4. Place the file in the project folder, and unzip (or decompress) the file `Tennis_Windows_xx.zip`.

### Train the agent 
Execute  the cells within `Tennis.ipynb` in order to initialize the environment with making necessary adjustments for the path of the UnityEnvironment `Tennis.exe` in the code, initialize the agent, and perform the training of the two agents.
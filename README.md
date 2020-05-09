# Reinforcement_Learning_Collaboration_and_Competition_Udacity_Project

### Project Details

In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01. Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation. Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping.

The task is episodic, and in order to solve the environment, the agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents). 

![Unity Environment](https://github.com/nathan-standafer/Reinforcement_Learning_Collaboration_and_Competition_Udacity_Project/raw/master/images/tennis.png)


### Getting Started

Please follow the instructions in the [DRLND GitHub repository](https://github.com/udacity/deep-reinforcement-learning#dependencies) to set up your Python environment. These instructions can be found in README.md at the root of the repository. By following these instructions, you will install PyTorch, the ML-Agents toolkit, and a few more Python packages required to complete the project.

The Uniy Environment was executed within Udacity's virtual machines.  To run on your own machine, download the environment that matches your operating system:
 - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
 - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
 - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
 - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)


### Instructions

The code is executed from the "Tennis.ipynb" notebook.  The code is documented, but can be ran by executing the cells in order.  The trainng loop cell needs to be ran multiple tiems to train the networks sufficiently to pass the project's requirements.


### Training Graphs

![Rewards Loss vs Epoch](https://github.com/nathan-standafer/Reinforcement_Learning_Collaboration_and_Competition_Udacity_Project/raw/master/images/rewardsvsepoch.png)

![Actor Loss vs Epoch](https://github.com/nathan-standafer/Reinforcement_Learning_Collaboration_and_Competition_Udacity_Project/raw/master/images/actorlossvsepoch.png)

![Critic Loss vs Epoch](https://github.com/nathan-standafer/Reinforcement_Learning_Collaboration_and_Competition_Udacity_Project/raw/master/images/criticlossvsepoch.png)


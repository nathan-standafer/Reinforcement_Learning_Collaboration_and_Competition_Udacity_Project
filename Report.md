# Project Report

### Learning Algorithm

The algorthinm consistes of two separate DDPG networks, one for each player.  Time steps are performed on the environments and a training batch is executed after each step.

The secret sauce here is to periodidally evaluate the networks and choose the better one.  This significantly increases the training stability and results in higher overall scores.

After an epoch of 1000 steps is complete, the two networks are evaluated by play a series of games againsts each other (limited to 1000 steps). The winner's network weights are copied onto the loser's network.

The following hyperparameters were used:
 - **lr_actor = .0005** The actor network's learning rage.  determined through trialnad error.
 - **lr_critic = .0005** The critic network's learning rage.  determined through trialnad error.
 - **steps_per_epoch = 1000** Enough steps to introduce significant updates to the networks before evaluating them.
 - **gamma = 0.99** Deep Q sstyle networks always seem to use .99.  It seems to work.
 - **tau = 0.001** A small value since target networks are updated after each step.
 - **batch_size = 128** Seems to work.  A smaller value would probably increase training time.
 - **epsilon_max = 0.75** A starting point for performing random actions.  High enough to still generate some positive rewards when training begions.
 - **epsilon_min = 0.1** After training for a period of time, still high enough to allow for some exporation.


### Plot of Rewards
![Rewards Loss vs Epoch](https://github.com/nathan-standafer/Reinforcement_Learning_Collaboration_and_Competition_Udacity_Project/raw/master/images/rewardsvsepoch.png)

![Actor Loss vs Epoch](https://github.com/nathan-standafer/Reinforcement_Learning_Collaboration_and_Competition_Udacity_Project/raw/master/images/actorlossvsepoch.png)

![Critic Loss vs Epoch](https://github.com/nathan-standafer/Reinforcement_Learning_Collaboration_and_Competition_Udacity_Project/raw/master/images/criticlossvsepoch.png)

The submission reports the number of episodes needed to solve the environment.

Ideas for Future Work

The submission has concrete future ideas for improving the agent's performance.

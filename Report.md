# Project Report

### Learning Algorithim

The algorithim consists of two separate DDPG (Deep Deterministic Policy Gradient) networks, one for each player.  Time steps are performed on the environments and a training batch is executed after each step.

After an epoch of 1000 steps is complete, the two networks are evaluated by play a series of games againsts each other (limited to 1000 steps). The winner's network weights are copied onto the loser's network.

The secret sauce here is to periodidally evaluate the networks and to overwrite the losing network's weights with the winner's weights.  This significantly increases the training stability and results in higher overall scores.

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

It took about 30 epochs of 1000 steps each to reach a point where the project's success criteria could be reached.  Additional training resulted in the agents reaching the maximum allowable steps and scores of the environment. After training, the agentes competed against each other for 100 episodes.  The maximums scores were achieved about 96 times.

![Rewards Loss vs Epoch](https://github.com/nathan-standafer/Reinforcement_Learning_Collaboration_and_Competition_Udacity_Project/raw/master/images/rewardsvsepoch.png)

![Actor Loss vs Epoch](https://github.com/nathan-standafer/Reinforcement_Learning_Collaboration_and_Competition_Udacity_Project/raw/master/images/actorlossvsepoch.png)

![Critic Loss vs Epoch](https://github.com/nathan-standafer/Reinforcement_Learning_Collaboration_and_Competition_Udacity_Project/raw/master/images/criticlossvsepoch.png)


### Ideas for Future Work

The environment is almost comletely solved with this implementation.  

Ocassionally the first player will miss the first serve, resulting in a very short game.  Selectively training against this scenario might train the networks to avoid this problem.

Training faster is always good. The hyperparameters could be updated to see if any additional efficiencies can be gained. The networks make use of Batch Normalization, which I think helps them train faster.  Using Dropout is a possibile addition.

I think the networks are more collaborative than competitive.  Defeating the opponent results in a shorter game, and a lower potential score.  There is no incentive to beat the opponent.  The incentive of this implementation is to return the ball in a manner that the opponent can successfully return it to that the ball can be kept in play as long as possible.  Updating the rewards to incentivize the player for force a miss by the opposing player might make the networks more competitive and less collaborative. 

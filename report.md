# Report

The algorithm used for the project is Deep Q-Learning.


### Hyperparameters

BUFFER_SIZE = int(1e5)  : replay buffer size

BATCH_SIZE = 64         : minibatch size

GAMMA = 0.99            # discount factor

TAU = 1e-3              # for soft update of target parameters

LR = 5e-4               # learning rate 

UPDATE_EVERY = 4        # how often to update the network	

n_episodes=2000         # maximum number of training episodes

max_t=1000              # maximum number of timesteps per episode

eps_start=1.0           # starting value of epsilon, for epsilon-greedy action selection

eps_end=0.01            # minimum value of epsilon

eps_decay=0.995         # multiplicative factor (per episode) for decreasing epsilon


### Deep Q network:
Used a network that maps state to action values with the following model architecture:

Input nodes (37 nodes)

Fully Connected Layer with ReLU activation (64 nodes)

Fully Connected Layer with ReLU activation (64 nodes)

Output nodes (4 nodes)

### Plot of rewards

Agent is able to receive an average reward (over 100 episodes) of at least +13:

Environment solved in 412 episodes. 

Average score: 13.04

![alt text](https://github.com/AlperTekeli/udacity-drl-navigation/blob/main/score.png)

### Ideas for Future Work

Following methods can be used to further improve the algorithm (explanations from Udacity DRL course content):

Deep Q-Learning tends to overestimate action values. Double Q-Learning has been shown to work well in practice to help with this:

- [Deep Reinforcement Learning with Double Q-Learning](https://arxiv.org/abs/1509.06461)

Deep Q-Learning samples experience transitions uniformly from a replay memory. Prioritized experienced replay is based on the idea that the agent can learn more effectively from some transitions than from others, and the more important transitions should be sampled with higher probability:

- [Dueling Network Architectures for Deep Reinforcement Learning](https://arxiv.org/abs/1511.06581)

Currently, in order to determine which states are (or are not) valuable, we have to estimate the corresponding action values for each action. However, by replacing the traditional Deep Q-Network (DQN) architecture with a dueling architecture, we can assess the value of each state, without having to learn the effect of each action:

- [Prioritized Experience Replay](https://arxiv.org/abs/1511.05952)



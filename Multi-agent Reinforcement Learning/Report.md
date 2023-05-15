# Project Report for Reinforcement Learning using Value based methods

[image1]: ./p3_collab-compet/scores_vs_episodes.jpg "Plot of Rewards"

## Learning Algorithm

The learning algorithm used is modified DDPG, which is an Actor-Critic method. 

Actor neural network with 2 fully connected hidden layers with 512 neurons and 256 neurons and ReLU activation and 1 outer layer with tanh activation is used. Layer Normalization was done after both hidden layers to improve stability. The size of the input layer is equal to the size of the state space which is 48 (combined state space for both agents). The size of the output layer is equal to the number of possible actions, which is 4 (combined action space for both agents).

Critic neural network with 2 fully connected hidden layers with 516 (512 + 4, which is the action size) neurons and 256 neurons and ReLU activation and 1 outer layer is used. The size of the input layer is equal to the size of the state space which is 48. The size of the output layer is 1, which is the Q-value.

Two neural networks are used each for actor and critic - one local and one target which gets updated using the local network using a soft update

Other hyperparameters chosen are 
- A replay buffer size 1000000 is used to store the experience replay
- Batch size 128 is used to trigger a weight update
- Gamma 0.99 is used to discount future rewards
- Tau 0.005 is used for soft update of target from the local to the target network
- A learning rate of 0.001 is used for both the local actor network and local critic network parameter update
- Epsilon parameters are used to reduce the noise as the learning progresses. A start value of epsilon of 1 was used and was decayed by 0.995 after every 1000 learning steps.


## Plot of Rewards
A plot of rewards per episode is included to illustrate that the agent is able to receive an average reward (over 100 episodes) of at least +0.5. The number of episodes required to solve the environment is 1858 episodes.

![Plot of Rewards][image1]

## Ideas for Future Work

Future improvements can be using
- Using Prioritized Experienced Replay
- Hyperparameter tuning to help the model converge quicker like
    - variable learning rate
    - batch size
    - buffer size

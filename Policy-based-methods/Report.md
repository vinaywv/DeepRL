# Project Report for Reinforcement Learning using Value based methods

[image1]: scores_vs_episodes.jpg "Plot of Rewards"

## Learning Algorithm

The learning algorithm used is DDPG, which is an Actor-Critic method. 

Actor neural network with 2 fully connected hidden layers with 400 neurons and 300 neurons and ReLU activation and 1 outer layer with tanh activation is used. The size of the input layer is equal to the size of the state space which is 33. The size of the output layer is equal to the number of possible actions, which is 4.

Critic neural network with 2 fully connected hidden layers with 404 (400 + 4, which is the action size) neurons and 300 neurons and ReLU activation and 1 outer layer is used. The size of the input layer is equal to the size of the state space which is 33. The size of the output layer is equal to the number of possible actions, which is 1.

Two neural networks are used each for actor and critic - one local and one target which gets updated using the local network using a soft update

Other hyperparameters chosen are 
- A replay buffer size 100000 is used to store the experience replay
- Batch size 128 is used to trigger a weight update
- Gamma 0.99 is used to discount future rewards
- Tau 0.001 is used for soft update of target from the local to the target network
- A learning rate of 0.0001 is used for the local actor network parameter update, while 0.001 is used for local critic network parameter update


## Plot of Rewards
A plot of rewards per episode is included to illustrate that the agent is able to receive an average reward (over 100 episodes) of at least +30. The number of episodes required to solve the environment is 136 episodes.

![Plot of Rewards][image1]

## Ideas for Future Work

Future improvements can be using
- Using Prioritized Experienced Replay
- Using synchronized learning using A2C method
- Using PPO

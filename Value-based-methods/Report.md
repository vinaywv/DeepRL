# Project Report for Reinforcement Learning using Value based methods

[image1]: score_vs_episodes.jpg "Plot of Rewards"

## Learning Algorithm

The learning algorithm used is DQN. A neural network with 2 fully connected hidden layers with 64 neurons and ReLU activation and 1 outer layer is used. The size of the input layer is equal to the size of the state space which is 37. The size of the output layer is equal to the number of possible actions, which is 4.

Two neural networks are used - one local and one target which gets updated using the local network after every few episodes

Other hyperparameters chosen are 
- A replay buffer size 100000 is used to store the experience replay
- Batch size 64 is used to trigger a weight update
- Gamma 0.99 is used to discount future rewards
- Tau 0.001 is used for soft update of target from the local to the target network
- A learning rate of 0.0005 is used for the local network parameter update
- Target network is updated after every 4 episodes
- Epsilon starts with 1.0 and a epsilon decay of 0.995 is used to decay the epsilon with each episode

## Plot of Rewards
A plot of rewards per episode is included to illustrate that the agent is able to receive an average reward (over 100 episodes) of at least +16. The number of episodes required to solve the environment is 942 episodes.

![Plot of Rewards][image1]

## Ideas for Future Work
The submission has concrete future ideas for improving the agent's performance.ission has concrete future ideas for improving the agent's performance.

Future improvements can be using
- Double DQN
- Prioritized experience replay
- Dueling DQN
- Rainbow

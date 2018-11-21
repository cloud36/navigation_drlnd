# Project 1: Navigation

### Introduction

The goal of this project is to train an agent to solve Unity's Banana Collector environment. To solve this taks a DQN and Double-DQN were implemented using PyTorch. 

## Learning Algorithm Overview

The primary learning algorithm used to solve this task was a Deep Q-Network. This is a reinforcement learning algorithm made popular in February 2015, by researchers at DeepMind. This algorithm combines deep learning and reinforcement learning to achieve super-human level control on various Atari games from raw pixels. 

Original Paper: https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf

#### Algorithm
DQN's extend traditional Q-Learning by using function approximation represented by a deep neural network, hence the name DQN. In addition to using a DNN to represent the state-action space, two other important modifications were made: experience replay and use of a target network. Both of these modifications were to help overcome what is known as the "deadly triad" coined by Richard Sutton. The deadly triad occurs when three elements are combined: bootstrapping, function approximation and off-policy learning. DQN has all three of these ingredients. 

- Experience Replay: Not only does experience replay help us decorrelate state-action pairs, which helps prevent the learning from oscillating or diverging,  but it can also help the learning algorithm converge faster and make more efficient use of its past experience. 
   
- Target Network: Another important addition is the use of a target network. Without the target network, a single DNN would be used to estimate both the current state value and the expected next state value. The problem arises when updating the parameters of the DNN. With the updated parameters, both the current state estimate and next state estimate may change, which in turn would make minimizing the loss function difficult -- think of chasing a moving target. 

#### Hyperparameters
- Gamma: Discount Factor = .99
    - With a discount factor of .99, this means that 99% of the next states reward is included in current states value estimation. 
- Alpha: Learning Rate = 5e-4
    - This controls the magnitude of steps gradient descent takes. A higher learning rate could lead to more oscillating at first. 
- Epsilon: 
    - For exploration versus exploitation. This starts at 1 to encourage exploration at beginning of game and decays to .01 by .95 each episode. 
- Buffer Size: Number of experiences to be stored in replay memory bank. 
- Batch Size: Number of samples to use for mini-batch stochastic gradient descent. 
- Tau: To control updating Local Network versus Target Network. 

#### Model Architecture

## Double DQN 

Double DQN is an improvement on the original DQN and it attempts to address overly optimistic q-function that is observed in DQN's. It is easy for a DQN to overestiamte the q-function because of the argmax operator in the TD Error update. To handle this Double DQN makes a simple modification by having another DNN estimate the value of the argmax operator i.e. we use DNN-1 to select the actions in th argmax operator and use another DNN (DNN-2) to estimate the value. To implement this we simple use our target and local DNNs. 

Read more about Double DQN's here: https://arxiv.org/pdf/1509.06461.pdf

### Plot of Rewards

Below we can see the average reward over the last 100 episodes for both DQN and Double DQN. It is interesting that they are very similar. It makes clear that Double DQN doesn't necessarily make for quicker convergence, but more stable learning. 

Inline-style: 
![alt text](https://github.com/cloud36/navigation_drlnd/blob/master/dqn_rewards.png "Logo Title Text 1")


### Future Improvements / Implementations 

1. Prioritized Experience Replay (PER)
2. Dueling DQN 
3. It would be interesting to see if observed human game play could lead to faster convergence. 
   
   

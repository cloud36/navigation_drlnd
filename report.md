# Project 1: Navigation

### Introduction

The goal of this project is to train an agent to solve Unity's Banana Collector environment. To solve this taks a DQN and Double-DQN were implemented using PyTorch. 

## Learning Algorithm Overview

The primary learning algorithm used to solve this task was a Deep Q-Network. This is a reinforcement learning algorithm made popular in February 2015, by researchers at DeepMind. This algorithm combines deep learning and reinforcement learning to achieve super-human level control on various Atari games from raw pixels. 

#### Algorithm
DQN's extend traditional Q-Learning by using function approximation represented by a deep neural network, hence the name DQN. In addition to using a DNN to represent the state-action space, two other important modifications were made: experience replay and use of a target network. Both of these modifications were to help overcome what is known as the "deadly triad" coined by Richard Sutton. The deadly triad occurs when three elements are combined: bootstrapping, function approximation and off-policy learning. DQN has all three of these ingredients. 

- Experience Replay: Not only does experience replay help us decorrelate state-action pairs, which helps prevent the learning from oscillating or diverging,  but it can also help the learning algorithm converge faster and make more efficient use of its past experience. 
   
- Target Network: Another important addition is the use of a target network. Without the target network, a single DNN would be used to estimate both the current state value and the expected next state value. The problem arises when updating the parameters of the DNN. With the updated parameters, both the current state estimate and next state estimate may change, which in turn would make minimizing the loss function difficult -- think of chasing a moving target. 

#### Hyperparameters
- Gamma: Discount Factor
- Alpha: Learning Rate
- Epsilon: For exploration versus exploitation
- Buffer Size: Number of experiences to be stored in replay memory bank. 
- Batch Size: Number of samples to use for mini-batch stochastic gradient descent. 
- Tau: To control updating Local Network versus Target Network. 

#### Model Architecture

## Double DQN 

### Plot of Rewards
Inline-style: 
![alt text](https://github.com/cloud36/navigation_drlnd/blob/master/dqn_rewards.png "Logo Title Text 1")


### Future Imporvements

1. Prioritized Experience Replay (PER)
2. Dueling DQN 
3. It would be interesting to see if observed human game play could lead to faster convergence. 
   
   

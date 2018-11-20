# Project 1: Navigation

### Introduction

The goal of this project is to train an agent to solve Unity's Banana Collector environment. To solve this taks a DQN and Double-DQN were implemented using PyTorch. 

### Learning Algorithm 

## DQN 
The primary learning algorithm used to solve this task was a Deep Q-Network. This is a reinforcment learning algorithm made popular by INSERT HERE. 

DQN's extend traditional Q-Learning by using function approximation represented by a deep neural network, hence the name DQN. In addition to using a DNN to represent the neural network, two other important modifications were made:

- Experience Replay: Experience replay is help in that in uncorrelated the consecutive states, this is important as x, y, z. 
   
- Target Network: Another important addition is the use of a target network. Without the target network, a single DNN would be used to estimate both the current state value and the expected next state value. The problem arises when updating the parameters of the DNN. With the updated parameters, both the current state estimate and next state estimate may change, which in turn would make minimizing the loss function difficult -- think of chasing a moving target. 

## Double DQN 

### Plot of Rewards

### Future Imporvements

1. Prioritized Experience Replay (PER)
2. Dueling DQN 
   
   

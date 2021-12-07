# Deep Reinforcement Learning Project 1: Navigation

## Project Goal
The goal is to navigate the 37 dimension state space collecting yellow bananas and avoiding blue bananas in order to score +13 over 100 consecutive episodes. Each yellow banana is worth +1 and each blue banana is -1

## RL Agent Description
Based on the instructions in the "Not Sure Where To Start?" guide, I used the source code from the "Deep Q Network Solution" ipython notebook of Lesson 2. This code uses a pretty vanilla DQN with experience replay and an epsilon greedy action selection as per earlier lessons in the course. The params are all set to default such that:

## Initial Params

- Buffer Size: 1e5
- Batch Size: 64
- Discount Factor: 0.99
- Soft Update: 1e-3
- Learning Rate: 5e-4
- Update Cycle: 4
- Epsilon: .99 (I played with some values and felt this was a good mix of exploration vs. exploitation)

## Deep Neural Net Description

The neural network has the following params (all default from the Lesson 2 solution):
- A linear fully-connected layer of state_size=37 and fc1_units=64
- A linear fully-connected layer of fc1_units=64 and fc2_units=64
- A linear fully-connected layer of fc2_units=64 and action_size=4

## Training
Training was done over 380 episodes with a final average score of 13.04. Here is the output from training:
```
Episode 100	Average Score: 2.31
Episode 100	Average Score: 2.31
Episode 200	Average Score: 7.79
Episode 300	Average Score: 10.76
Episode 380	Average Score: 13.04 

You did it! Solved in 380 episodes!	avg score: 13.04
```
A plot of this training can be seen in the [Navigation ipython Notebook](Navigation.ipynb)

## Testing
Testing was done over 25 episodes using weights loaded from the model saved during training. Below are the results of testing:
```
episode num: 1	 score: 15.00
episode num: 2	 score: 11.00
episode num: 3	 score: 4.00
episode num: 4	 score: 17.00
episode num: 5	 score: 2.00
episode num: 6	 score: 11.00
episode num: 7	 score: 18.00
episode num: 8	 score: 19.00
episode num: 9	 score: 18.00
episode num: 10	 score: 18.00
episode num: 11	 score: 13.00
episode num: 12	 score: 9.00
episode num: 13	 score: 16.00
episode num: 14	 score: 16.00
episode num: 15	 score: 10.00
episode num: 16	 score: 15.00
episode num: 17	 score: 18.00
episode num: 18	 score: 9.00
episode num: 19	 score: 12.00
episode num: 20	 score: 15.00
episode num: 21	 score: 19.00
episode num: 22	 score: 18.00
episode num: 23	 score: 15.00
episode num: 24	 score: 13.00
episode num: 25	 score: 17.00
```
A plot of this testing can be found in the [Navigation ipython Notebook](Navigation.ipynb)

### Future Work Considerations
The most obvious path for improving this implementation is optimizing the current parameters. I could also improve performance by adding other extensions to the DQN algorithm, such as dueling DQN or prioritized experience replay. Another option is to try learning from pixels as already suggested as a next step.

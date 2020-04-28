##  Reinforcement Learning!

Reinforcement Learning is a branch of Machine Learning, also called Online Learning.
It is about taking suitable action to maximize reward in a particular situation. It is employed by various software and machines to find the best possible behavior or path it should take in a specific situation. 
Reinforcement learning differs from the supervised learning in a way that in supervised learning the training data has the answer key with it so the model is trained with the correct answer itself whereas in reinforcement learning, there is no answer but the reinforcement agent decides what to do to perform the given task. In the absence of training dataset, it is bound to learn from its experience.

**Example**: The problem is as follows: We have an agent and a reward, with many hurdles in between. The agent is supposed to find the best possible path to reach the reward. The following problem explains the problem more easily.

<img src="https://media.geeksforgeeks.org/wp-content/uploads/Untitled-95.png">

The above image shows robot, diamond and fire. The goal of the robot is to get the reward that is the diamond and avoid the hurdles that is fire. The robot learns by trying all the possible paths and then choosing the path which gives him the reward with the least hurdles. Each right step will give the robot a reward and each wrong step will subtract the reward of the robot. The total reward will be calculated when it reaches the final reward that is the diamond.

**Main points in Reinforcement learning**

- **Input**: The input should be an initial state from which the model will start
- **Output**: There are many possible output as there are variety of solution to a particular problem
- **Training**: The training is based upon the input, The model will return a state and the user will decide to reward or punish the model based on its output.
- The model keeps continues to learn.
- The best solution is decided based on the maximum reward.

**Difference between Reinforcement learning and Supervised learning**

| REINFORCEMENT LEARNING |	SUPERVISED LEARNING |
| ---------------------- | -------------------- |
| Reinforcement learning is all about making decisions sequentially. In simple words we can say that the output depends on the state of the current input and the next input depends on the output of the previous input	| In Supervised learning the decision is made on the initial input or the input given at the start |
| In Reinforcement learning decision is dependent, So we give labels to sequences of dependent decisions | Supervised learning the decisions are independent of each other so labels are given to each decision. |
| Example: Chess game	| Example: Object recognition |


**Types of Reinforcement**:
 There are two types of Reinforcement:

- **Positive**:  Positive Reinforcement is defined as when an event, occurs due to a particular behavior, increases the strength and the frequency of the behavior. In other words it has a positive effect on the behavior.

Advantages of reinforcement learning are:

	- Maximizes Performance
	- Sustain Change for a long period of time

Disadvantages of reinforcement learning:

	- Too much Reinforcement can lead to overload of states which can diminish the results

- **Negative**: Negative Reinforcement is defined as strengthening of a behavior because a negative condition is stopped or avoided.

Advantages of reinforcement learning:

	- Increases Behavior
	- Provide defiance to minimum standard of performance

Disadvantages of reinforcement learning:

	- It Only provides enough to meet up the minimum behavior

- **Various Practical applications of Reinforcement Learning** 

	- RL can be used in robotics for industrial automation.
	- RL can be used in machine learning and data processing
	- RL can be used to create training systems that provide custom instruction and materials according to the requirement of students.

RL can be used in large environments in the following situations:

1. A model of the environment is known, but an analytic solution is not available;
2. Only a simulation model of the environment is given (the subject of simulation-based optimization);[6]
3. The only way to collect information about the environment is to interact with it.


In this repo, I will implement the following Reinforcement Learning models:

- Upper Confidence Bound (UCB)
- Thompson Sampling
# Project  Report


In this project, the Deep Q-Networks algorithm named [DQN](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) is implemented to train an agent for navigating itself. The below figure shows the outcome of this project via using the graphics. The agent before training is seen in the left side, and the trained one is in the right side.

Random Banana Agent         |  DQN Banana Agent 
:-------------------------:|:-------------------------:
![](random.gif)  |  ![](smart.gif)


### Environment
Unity's ML Agents package is utilized in the project to train the agent on the environment named Banana. In this environment, yellow and blue bananas are randomly placed on the platform. Moreover, position of the agent is also randomly determined. This agent perceives a 37-dimensional vector as its own state. Velocity and the ray-based observations are kept in the state. Moreover, one may use the pixels in the enviroment as the input state. The goal of this task is to get an average score of +13 over 100 consecutive episodes.

### Methodology
The Deep Q-Networks is an algorithm in which it is trained to find out the optimum Q values. It can bee too complex depending on a task. In this project, we keep it simple since our environment provides us state values in 37-dimensional space. DQN algorithm is implemented by using Pytorch and Python 3. The neural network consists of 3 fully connected layers followed by ReLu actiovations except the last layer which outcomes a 4-dimensional vector for actions. Each hidden layer contains 64 units. Adam is selected as an optimizer.

  - Experience Replay  : Our agent takes actions orderly. Therefore, probability of selecting the next action may be affected by the previous one. To eliminate this correlation effect we utilize the replay buffer which is a fixed size buffer to store experiences.
  - Fixed Q-Targets: Two identical Q-Networks are created for the agent: a local and a target. The local network is softly updated every **n** steps with parameters of the target network. In this way, similar to replay buffer, we can decrease correlation among selection of actions. 

These techniques are utilized to train out banana collector agent. Due to simplicity of the input state and the network we mentioned above, we prefer to use CPU in order to train our agent.

### Results
We used the hyperparameters as the following:
  - BUFFER_SIZE = int(1e5)  # replay buffer size
  - BATCH_SIZE = 512        # minibatch size
  - GAMMA = 0.99            # discount factor
  - TAU = 1e-3              # for soft update of target parameters
  - LR = 5e-4               # learning rate 
  - UPDATE_EVERY = 4        # how often to update the network
  
Our agent is capable of solving the task after the episode **495**. The result of the DQN algorithm is the following:  
  > Episode 100	Average Score: 0.36  
  Episode 200	Average Score: 3.59  
  Episode 300	Average Score: 6.97  
  Episode 400	Average Score: 9.74  
  Episode 500	Average Score: 11.50  
  Episode 595	Average Score: 13.01  
  Environment solved in 495 episodes!	Average Score: 13.01 
  
The average score value is calculated by averaging scores in the last 100 episodes.
![Rewards](rewards.png)


#### The learning rate effect
A learning rate value can vary depending on what kind of task the algorithm is train on. Therefore, different values are selected for the learning rate to see how it behaves during training. We set the maximum number of episodes to 500 since our aim is to see the effect of it. When we observe the following figure, we see that smaller learning rates are better for learning in this task. 

![LR effect](lr_effect.png)

#### The buffer size effect
Apart from the learning rate value, buffer size can also play an important role for learning. Therefore, an experiment is conducted to see whether or not is it important. We set the maximum number of episodes to 500 since our aim is to see the effect of it.
![BUFFER effect](buffer_size_effect.png)

As you can see in the above figure, decreasing the buffer size value leads to a worse performance in learning. Therefore, it can be said that if you have enough memory, then you should probably set the buffer size to a higher values.

### Conclusion
Using Pytorch and Unity's ml-agents in this project is quite impressive. The followings can be done as a future work:

  - Grid search can be applied to find the optimum hyperparameters
  - Learning from pixels: instead of using ray based perception, the agent can be trained via using the pixels.
  - Double DQN or Prioritized Experience Replay can be studied as a future work.



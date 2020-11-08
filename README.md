# Deep reinforcement learning for collecting bananas

## Introduction 
This is the first project of Udacity-Deep Reinforcement Learning Course. The main goal is to train an agent via a DQN algorithm so that the yellow bananas can be collected. There are also blue bananas on the platform. They should not be collected since the reward of collecting yellow bananas is +1 where the blue bananas is -1. There are four actions in the environment: 
- **`0`** - move forward.
- **`1`** - move backward.
- **`2`** - turn left.
- **`3`** - turn right.

These actions are taken by considering an input, 37-dimensional representation. This representation(state) contains information of an agent such as velocity and ray-based perception of the agent.

### Termination Criteria

The task is episodic. That means an agent should obtain an average score of +13 over 100 consecutive episodes.

## Let's go!

At first, we should obtain the environment. Please download the appropriate version, then place it in the path of Navigation.ipynb.
  - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
  - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
  - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
  - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)
    
  (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

  (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux_NoVis.zip) to obtain the environment.
  
  -Open the notebook named Navigation.ipynb
  -In the second cell, you should write your path for Banana environment that we mentioned above. 
  -Then you may execute each cell orderly.
  -After the seciton 4, our ml-agent is trained. If you want to use pre-trained weights, follow the below instructions.

## Using a pretrained version
If you are impatient, then you may use the pre-trained model parameters in the repository named checkpoint-cpu-<Learning-Rate>.pt. All you need to do is to set USE_PRETRAIN variable to True. This variable can be found in the beginning of the 4th section in Navigation.ipynb notebook.
  
  
If you are struggle to work on this project, please just open an issue. Look forward to hear about your nice experiences!

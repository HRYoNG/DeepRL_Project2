# Deep Reinforcement Project #2 - Udacity DeepRL Nanodegree course

1. Project Details

   For this project, you will work with the Reacher environment in which a double-jointed arm can move to target locations. 
   20 identical agents should maintain its position at the target location for as many time steps as possible.   
   
   - Reward : +0.1 for each step that the agent's hand is in the goal location

   - State Space : The state space has 33 dimensions and contains the agent's position, rotation, velocity, and angular velocities of the arm.

   - Vector Action Space (continous) : Each action is a vector with four numbers ranging from -1 to +1, corresponding to torque applicable to two joints.

   - Goal : Environment is solved when the average of average scores over 100 episodes is at least +30.
            The average score means the average of each 20 agents' scores in one episode.
 

2. Getting Started

    - File list  : ① Continuous_Control.ipynb ② ddpg_agent.py ③ model.py ④ checkpoint_actor.pth ⑤ checkpoint_critic.pth

    - Download the environment from one of the links below. You need only select the environment that matches your operating system:

        Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
        
        Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
        
        Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
        
        Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)
        
        (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

        (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip) (version 2) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)


3. Instructions

   - Follow the instructions in 'Continuous_Control.ipynb'.
   - Run the codes below '4. It's Your Turn!' in 'Continuous_Control.ipynb' to check the trained agent.
   - 'ddpg_agent.py','model.py', 'checkpoint_actor.pth' and 'checkpoint_critic.pth' should be included in the same project with 'Continuous_Control.ipynb'.
   - Experiment results of the trained model was already recorded in the notebook files.
   - checkpoint_actor.pth' and 'checkpoint_critic.pth contain trained networks' weights.

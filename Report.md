# Learning Algorithm

DDPG algorithm is used for this project.
### DDPG algoritm


The code used for this project is based on the DDPG code in the DRLND GitHub repository as the project guide <'Not sure where to start?'>.
Several amendments below were made in order to utilize 20 agents at the same time.

### 1st. Attempt

I amended the code to make 20 agents able to share a replay buffer and update the actor and critic networks 10 times after every 20 timesteps.

Second, gradient clipping was applied when training the critic network. The corresponding snippet of code was as follows:


With these amendments I could verify that this DDPG code runs in the environment of the project.

However I couldn't get successful learning result. the first result I got was just below.

![image](https://user-images.githubusercontent.com/55370676/195717141-15e0b087-d59e-40a4-8696-b548f12422fd.png)


### 2nd. Attempt 
So, I tried to modify Batch Normalization

![image](https://user-images.githubusercontent.com/55370676/195717347-4565260b-5c11-4343-8548-e7ab20a30201.png)


### 3rd. Attempt 
So, I tried to apply an epsilon parameter to decay the noise level over time because the algorithm don't seem to be converged.
This decay mechanism ensures that more noise is introduced earlier in the training process (i.e., higher exploration), and the noise decreases over time as the agent gains more experience (i.e., higher exploitation). The starting value for epsilon and its decay rate are two hyperparameters that were tuned during experimentation.


After you have verified that your DDPG code runs, try a few long training sessions while running your code on CPU. If your agent fails to learn, try out a few potential solutions by modifying your code. 

# Plot of Rewards


# Ideas for Future Work
Trust Region Policy Optimization (TRPO) and Truncated Natural Policy Gradient (TNPG) should achieve better performance. You may also like to write your own implementation of Proximal Policy Optimization (PPO), which has also demonstrated good performance with continuous control tasks.
You may also like to explore the (very!) recent Distributed Distributional Deterministic Policy Gradients (D4PG) algorithm as another method for adapting DDPG for continuous control.



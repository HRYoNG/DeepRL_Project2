# Learning Algorithm


### DDPG algorithm
![image](https://user-images.githubusercontent.com/55370676/195748515-6884c155-7a43-4fd8-8095-776257549077.png)

DDPG algorithm is used for this project. The critic in DDPG is used to approximate maximizer over the Q values of the next state, not as a learned baseline.
DDPG uses a replay buffer and soft updates to the target network to get a faster convergence. 

The project code is based on the basic DDPG code in the DRLND GitHub repository as the project guide <'Not sure where to start?'>.
Several amendments and adjustments below were made in order to get converging results.

### 1st. Attempt

#### Relay buffer and Gradient Clipping

I amended the code to make 20 agents able to share a replay buffer and update the actor and critic networks 10 times after every 20 timesteps.
The function Step() decides to learn accoring to the parameter UPDATE_CYCLE = 20, SAMPLE_NUM = 10 in ddpg_agent.py.

Gradient clipping was applied when training the critic network. (Agent.learn() in ddpg_agent.py)

    torch.nn.utils.clip_grad_norm_(self.critic_local.parameters(), 1)
    
With these amendments I could verify that this DDPG code runs in the environment of the project.

However the learning result wasn't successful.

![image](https://user-images.githubusercontent.com/55370676/195717141-15e0b087-d59e-40a4-8696-b548f12422fd.png)


### 2nd. Attempt 
#### Batch Normalization
I tried to add Batch Normalization layer to get better learning performance. 
Normalizing Layers were added in both actor and critic network. (line 40, line 73 in model.py)

    self.bn1 = nn.BatchNorm1d(fc1_units)
    ...
    def forward(self, state):
        """Build an actor (policy) network that maps states -> actions."""
        x = F.relu(self.bn1(self.fc1(state)))
        x = F.relu(self.fc2(x))
        return F.tanh(self.fc3(x))
    
It seemed that the agents could get little bit higher scores than attempt 1. 
It still didn't work well. Learning was too slow and not successful.
![image](https://user-images.githubusercontent.com/55370676/195717347-4565260b-5c11-4343-8548-e7ab20a30201.png)


### 3rd. Attempt 
#### Higher Exploitation
I assumed that the main reason for not converging result was too much exploration made during the training process.
So, I tried to adjust exploitation and exploration ratio by applying an epsilon parameter to decay the noise.(in ddpg_agent.py)

    EPS_START = 1.0
    EPS_END = 0.05
    EPS_DECAY_RATE = 1e-6
    
    def act(self, state, add_noise=True):
        ...
        if add_noise:
            action += self.noise.sample() * self.epsilon  
        return np.clip(action, -1, 1)
        
Added epsilon parameter decreased the noise over time as the agent gains more experience.
Then it started to converge and get higher scores as time goes by.

The environment was solved as you can see in the plot below.

# Plot of Rewards

![image](https://user-images.githubusercontent.com/55370676/195745794-e02640f7-4b48-49f1-85d4-0b07af199a40.png)

The agent solved the environment at the 7th episode, since the average of the average scores from episodes 8 to 107 (inclusive) was greater than +30.
The detail process is written in "4. ② Train the Agent with DDPG" of <Continuous_Control.ipynb>


# Ideas for Future Work
Advanced algorithms such as Trust Region Policy Optimization (TRPO), Truncated Natural Policy Gradient (TNPG) can achieve better performance according to [Benchmark](https://arxiv.org/abs/1604.06778).

Distributed Distributional Deterministic Policy Gradients ([D4PG](https://openreview.net/forum?id=SyZipzbCb)) algorithm as another method for adapting DDPG can be used for this continuous control project.


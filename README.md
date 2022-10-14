# Deep Reinforcement Project #2 - Udacity DeepRL Nanodegree course

### 1. Project Details

   For this project, you will work with the Reacher environment in which a double-jointed arm can move to target locations. 
   20 identical agents should maintain its position at the target location for as many time steps as possible.   
   
   - Reward : +0.1 for each step that the agent's hand is in the goal location

   - State Space : The state space has 33 dimensions and contains the agent's position, rotation, velocity, and angular velocities of the arm.

   - Vector Action Space (continous) : Each action is a vector with four numbers ranging from -1 to +1, corresponding to torque applicable to two joints.

   - Goal : Environment is solved when the average of average scores over 100 episodes is at least +30.
            The average score means the average of each 20 agents' scores in one episode.
 

### 2. Getting Started

    - File list  : ① Continuous_Control.ipynb ② ddpg_agent.py ③ model.py ④ checkpoint_actor.pth ⑤ checkpoint_critic.pth

        
        
#### Dependencies

To set up your python environment to run the code in this repository, follow the instructions below.

① Create (and activate) a new environment with Python 3.6.

	- __Linux__ or __Mac__: 
	```bash
	conda create --name drlnd python=3.6
	source activate drlnd
	```
	- __Windows__: 
	```bash
	conda create --name drlnd python=3.6 
	activate drlnd
	```
	
② If running in **Windows**, ensure you have the "Build Tools for Visual Studio 2019" installed from this [site](https://visualstudio.microsoft.com/downloads/).  This [article](https://towardsdatascience.com/how-to-install-openai-gym-in-a-windows-environment-338969e24d30) may also be very helpful.  This was confirmed to work in Windows 10 Home.  

③ Follow the instructions in [this repository](https://github.com/openai/gym) to perform a minimal install of OpenAI gym.  
	- Next, install the **classic control** environment group by following the instructions [here](https://github.com/openai/gym#classic-control).
	- Then, install the **box2d** environment group by following the instructions [here](https://github.com/openai/gym#box2d).
	
④ Clone the repository (if you haven't already!), and navigate to the `python/` folder.  Then, install several dependencies.  
    ```bash
    git clone https://github.com/udacity/deep-reinforcement-learning.git
    cd deep-reinforcement-learning/python
    pip install .
    ```

⑤ Create an [IPython kernel](http://ipython.readthedocs.io/en/stable/install/kernel_install.html) for the `drlnd` environment.    
    ```bash
    python -m ipykernel install --user --name drlnd --display-name "drlnd"
    ```

⑥ Before running code in a notebook, change the kernel to match the `drlnd` environment by using the drop-down `Kernel` menu. 


### 3. Instructions
   - Follow the instructions in 'Continuous_Control.ipynb'.
   - Run the codes below '4. It's Your Turn!' in 'Continuous_Control.ipynb' to check the trained agent.
   - 'ddpg_agent.py','model.py', 'checkpoint_actor.pth' and 'checkpoint_critic.pth' should be included in the same project with 'Continuous_Control.ipynb'.
   - Experiment results of the trained model was already recorded in the notebook files.
   - checkpoint_actor.pth' and 'checkpoint_critic.pth contain trained networks' weights.

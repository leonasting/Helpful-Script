# Setting Tensorboard for stable baseline 3

1. Installation for stable baseline3 and pre requisites need to handled before.

2. In the code following code segment needs to be present.
```
import os
from stable_baselines3 import DDPG
from stable_baselines3.common.vec_env import DummyVecEnv

# Make your directories first
log_path = os.path.join('Training','Logs')# It is the same path which will be later used to host tensor board from cli.


env = gym.make(environment_name)
env = DummyVecEnv([lambda: env])
model = DDPG('MultiInputPolicy', env, verbose = 1,tensorboard_log=log_path) # Here the tensor board is linked

```
3. Setup a Tunnel to HPC
PortID:6006 #Default Port for tensorboard else can be changed
- **Note** coe-hpc1.sjsu.edu  or coe-hpc.sjsu.edu 
```
SSH -L <PortID>:localhost:<PortID> <StudentID>@coe-hpc1.sjsu.edu
```
(Optional) If you hos the tensorbord form another node 
Node ID: If you host the server
```
SSH -L <PortID>:localhost:<PortID> StudentId@<NodeID>
```

4. Command to start hosting the tensorbord. ** Note:** It is hosted on 6006 port if the port is not mentioned
```
tensorboard --logdir=Training/Logs
```

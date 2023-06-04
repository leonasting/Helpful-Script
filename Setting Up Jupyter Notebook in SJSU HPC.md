# Setting Up Jupyter Notebook on SJSU HPC

**Reference:** [SJSU official HPC Cluster Page](http://coe-hpc-web.sjsu.edu/)

There are following steps to work on HPC

1. Connection to SSJU server

**Session 1:**

2. Connect to HPC 

	a. If you use MAC/Linux  - Default Shell
	
	b. If you use Windows - Use poweshell (Update till the latest connect)
	
3. Use Slurm command to create interactive session(this session will be accessed later)

**Session 2:**

4. Create another session to create local tunnel from you own PC to Server
5. Create tunnel from the current session to the earlier session  
6. (Optional) If you use conda environment change the conda environment 
7.  Settup No-browser session of jupyter notebook / jupyter lab based on you preference.

# Connection to SJSU server

If you are present inside SJSU campus like library or engineering building you can skip this step.
You need VPN(cisco anyconnect) to sjsu servers.[Reference](https://www.sjsu.edu/it/services/network/internet-access/vpn.php)

- Cisco AnyConnect Secure Mobility Client 
- Url : vpn.sjsu.edu
- Group : Student-SSO

Check for Student Sign on
# Connect to HPC

Shell connect command


	
``
SSH  <Student ID> @ coe-hpc.sjsu.edu
or 
SSH  <Student ID> @ coe-hpc1.sjsu.edu (Note:1)
``

**Note** ``<Student ID>`` is a Place holder for student id like  **015898XXX**


# Use Slurm command to create interactive session

- gres -> For GPU
- c -> Number of cpu nodes
- n -> Number of tasks
- N -> Number of Nodes

### Exampe l with GPU:
``
 srun -p gpu --gres=gpu -n 1 -N 1 -c 2 --pty /bin/bash
``
### Exampe 2 with CPU:
``
 srun -p  -n 1 -N 1 -c 2 --pty /bin/bash
``

You will be allocated a particular Node:

```StudentID@NodeID``` -> Remember the node

**Note:** NodeID is important



# Create another session to create local tunnel from you own PC to Server
PortID Range - 10000 - 99999

- **Note** coe-hpc1.sjsu.edu  or coe-hpc.sjsu.edu 

```
SSH -L <PortID>:localhost:<PortID> <StudentID>@coe-hpc1.sjsu.edu
```
# Create tunnel from the current session to the earlier session
Use the same PortID.

```
SSH -L <PortID>:localhost:<PortID> StudentId@<NodeID>
```

**Note** Port can beoccupied, so do check when setting up, if  it is succesfull.

# (Optional) Change the conda environment
``
Conda activate enviroment-name
``

#  Setup No-browser session of jupyter notebook / jupyter lab 
``
jupyter notebook --no-browser --port=<PortID>
``

``
jupyter lab --no-browser --port=<PortID>
``



It will provide you with the link to open jupyter notebook/ lab landing page. It has token so use the link.

example:
 ``
 http://localhost:<PortID>/?token=74b92019ae86040d0299fa71670febff25366bde605218e2
``
## After Setup
Just start any python IPYNB file to check if the enviroment is working 

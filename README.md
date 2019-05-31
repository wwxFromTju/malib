[![License](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)

# Multi-Agent Reinforcement Learning Framework

This Framework aims to provide an easy to use toolkit for
Multi-Agent Reinforcement Learning research.

Overall architecture:

![processes](./docs/framework_architecture.png)

Environment: There are two differences for Multi-Agent Env Class: 1. The step(action_n) accepts n actions at each time; 2. The Env class needs a MAEnvSpec property which describes the action spaces and observation spaces for all agents.



Agent: the agent class has no difference than common RL agent, it uses the MAEnvSpec from Env Class to init the policy/value nets and replay buffer.

MASampler: Because the agents have to rollout simultaneously, a MASampler Class is designed to perform the sampling steps and add/return the step tuple to each agent's replay buffer.

MATrainer: In single agent, the trainer is included in the Agent Class. However, due to the complexity of Multi-Agent Training, which has to support independent/centralized/communication/opponent modelling, it is necessary to have a MATrainer Class to abstract these requirements from Agent Class. This is the core for Multi-agent training.

## Installation


* Using Local Python Environment:

Required Python Version: 3.6.5

 ```shell
cd maci
sudo pip3 install -r requirements.txt
sudo pip3 install -e .
 ```

* Using Conda Environment:

```shell
cd maci
conda env create --file=environment.yml
conda activate malib
pip install -e .

```


## Run Example

```shell
cd examples
python3 run_agents.py
```


## Reference Projects
The project implementation has referred much and adopted some codes from the following projects:
[agents](https://github.com/tensorflow/agents)
,[maddpg](https://github.com/openai/maddpg)
,[softlearning](https://github.com/rail-berkeley/softlearning)
,[garage](https://github.com/rlworkgroup/garage)
,[markov-game](https://github.com/aijunbai/markov-game). Thanks a lot!
  
    

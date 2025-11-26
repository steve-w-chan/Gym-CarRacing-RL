# CarRacing-v3 Deep Reinforcement Learning Project
Training SAC / PPO / DQN agents on Gymnasium CarRacing-v3

# Project Overview
This repository implements vision-based reinforcement learning agents for
Gymnasium's CarRacing-v3 environment.

We train three algorithms:
- SAC (Soft Actor-Critic)
- PPO (Proximal Policy Optimization)
- DQN (Discrete-actions baseline)

The project supports:
- Modular per-algorithm notebooks
- Live reward plotting
- Checkpoint saving
- Evaluation pipeline (mean reward, variance)
- Demo video recording

# Repository Structure
```text
Gym-CarRacing-RL/
│
├── SAC/
│   ├── carracing_sac.ipynb
│   ├── models_SAC/       # Saved model checkpoints
│   ├── logs_SAC/         # Reward logs
│   └── videos_SAC/       # Demo videos
│
├── PPO/
│   ├── carracing_ppo.ipynb
│   ├── models_PPO/
│   ├── logs_PPO/
│   └── videos_PPO/
│
├── DQN/
│   ├── carracing_dqn.ipynb
│   ├── models_DQN/
│   ├── logs_DQN/
│   └── videos_DQN/
│
├── best_model/
│   ├── best_sac/
│   ├── best_ppo/
│   └── best_dqn/
|
└── README.md
```

# Training
Training progression follows:
```text
0 → 300k steps   
300k → 600k  
600k → 1M
1M → 2M
...
```

Each stage:
- Loads previous checkpoint
- Trains additional timesteps
- Updates live reward plot
- Saves new checkpoint

# Evalution
To evaluate a checkpoint:
```python
evaluate_checkpoint(300000)
```
This will:
- run 10 evaluation episodes
- compute:
  - mean reward
  - variance
- store logs in logs_SAC/

# Demo
Videos are saved in:
```text
SAC/videos_SAC/
PPO/videos_PPO/
DQN/videos_DQN/
```

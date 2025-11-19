# CarRacing-v2 Deep Reinforcement Learning Project
Training SAC / PPO / DQN agents on Gymnasium CarRacing-v2

# Project Overview
This repository implements vision-based reinforcement learning agents for
Gymnasium's CarRacing-v2 environment.

We train three algorithms:
- SAC (Soft Actor-Critic)
- PPO (Proximal Policy Optimization)
- DQN (Discrete-actions baseline)

The project supports:
- Modular per-algorithm notebooks
- Live reward plotting
- Checkpoint saving (100k → 1M steps)
- Evaluation pipeline (mean reward, variance)
- Demo video recording

# Repository Structure
```text
Gym-CarRacing-RL/
│
├── sac/
│   ├── carracing_sac.ipynb
│   ├── models_SAC/       # Saved model checkpoints
│   ├── logs_SAC/         # Reward logs
│   └── videos_SAC/       # Demo videos
│
├── ppo/
│   ├── carracing_ppo.ipynb
│   ├── models_PPO/
│   ├── logs_PPO/
│   └── videos_PPO/
│
├── dqn/
│   ├── carracing_dqn.ipynb
│   ├── models_DQN/
│   ├── logs_DQN/
│   └── videos_DQN/
│
└── README.md
```

# Training
Training progression follows:
```text
0 → 100k steps  
100k → 300k  
300k → 600k  
600k → 1M
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
- run 5 evaluation episodes
- compute:
  - mean reward
  - variance
  - best/worst episode
- store logs in logs_SAC/

# Demo
Videos are saved in:
```text
videos_SAC/
videos_PPO/
videos_DQN/
```

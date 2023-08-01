# Mario Bros Agent RL Project - PPO with Stable Baselines 3

This repository contains the code and resources for training a Mario Bros agent using the Proximal Policy Optimization (PPO) algorithm with the Stable Baselines 3 framework. The agent learns to navigate and complete levels in the classic Super Mario Bros game, achieving increasingly better performance through reinforcement learning.

![Demo](agent_demo.gif)

## Requirements

* [Gym](https://www.gymlibrary.dev/)
* [Gym-super-mario-bros 7.3.0](https://pypi.org/project/gym-super-mario-bros/)
* [Nes_py](https://pypi.org/project/nes-py/)

## Preprocessing the environment

* Reduce the Action Space to 7 possible actions, instead of 256
* Grayscale the observations : (1 color channel to process instead of 3)
* Stack the observations to link them in time : The agent can evaluate the motion of ennemies
* Use the DummyVecEnv wrapper to allow multiple environments to train in parallel

## Create the model

I used the PPO model implemented in the stable-baselines3 library. The learning_rate 0.000001 gave me good results without any further hyperparameter tuning

## Train and test the model

I have only trained the model for 100000 timesteps (around 30 minutes). As a result, if the agent is trying to move forward, he is still stuck against some obstacles. Therefore, training for a longer period of time and possibly with a smaller learning rate should significantly increase the performance of the Mario agent. Don't hesitate to contact me to get the already trained model, or for any help with the gym library (which is quite confusing sometimes 😉) 
---
tags:
- programming/machine-learning/reinforcement-learning
- ruff-note
---
Unsupervised RL is very similar to supervised [[Reinforcement Learning|RL]]. Both assume that the underlying environment is described by a Markov Decision Process or a Partially Observed MDP, and both aim to maximize rewards.

The main difference is that supervised RL assumes that supervision is provided by the environment through an extrinsic reward while unsupervised RL defines an intrinsic reward through an extrinsic reward while unsupervised RL defines an intrinsic reward through a self-supervised task. Like supervision in NLP and vision, supervised rewards are either engineered or provided as labels by human operators which are hard to scale and limit the generalization of RL algorithms to specific tasks.

Most unsupervised RL algorithms know to date can be classified into three categories:
- knowledge based 
- data based
- competence based

Knowledge based methods maximize the prediction error or uncertainty of a predictive model. Data based methods maximize the diversity of observed data. Competence based methods maximize the mutual information between states and some latent vector often referred to as the skill or task vector


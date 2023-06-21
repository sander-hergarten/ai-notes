The Dreamer papers describe a system in which a world model predicts the environments future state using given the prior state and an action. This world model is then used to train an actor critic model which increases sample efficiency.

Since the world model is required to learn an internal state of the environment it should be possible to take advantage of this to assimilate a policy.

This is the structure of the world model in the Paper:
![[Pasted image 20230530220722.png]]
I will add another sequence model (sequence model beta) in addition to the action predictor:
![[Pasted image 20230530220851.png]]
This model can be trained using multiple routines to be both capable of offline as well as online learning. 
![[Training Routines]]

The losses for each of the routines are described in rough detail in the diagram below:
![[Pasted image 20230530221304.png]]
This figure does not describe the reinforcement learning loss as i have not yet decided which RL algorithm would be the most appropriate. As such the figure is not completely correct but should explain the idea of the different parts of the model.

# Goals 
Through learning of the world models internal representation this RL agent should be able to learn a true policy that is descriptive and as robust as the world models predictions.  In addition it is easier to debug as the auxiliary outputs make it easy to monitor the models performance and can provide utility beyond next action prediction. Through blind interactions with the environment multiple steps could be predicted without the need of the environments feedback. 

The model would still be capable of diverse domain mastery as described in Dreamer V3.

# Open Questions
- What RL algorithm to use
- How to determine switching from online/ offline training to autoregressive training. 
- Determining realistic blind step count in online environment.
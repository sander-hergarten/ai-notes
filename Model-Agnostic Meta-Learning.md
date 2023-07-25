---
tags:
- programming/machine-learning/meta-learning
- ruff-note
aliases:
- MAML
- maml
- model agnostic meta learning
- model-agnostic meta-learning
---
## Description
Maml is a model agnostic [[Meta Learning]] algorithm. It works on optimiser based meta-learning


MAML is an influential design following this pattern. Its inner-loop is a policy gradient algorithm whose initial parameters are the meta-parameters $\phi_0=\theta$. The key insight is that such an inner-loop is a differentiable function of the initial parameters, and therefore the initialization can be optimized with gradient descent to be a good starting point for learning on tasks from the task distribution . When adapting to a new task, MAML collects data using the initial policy and computs an updated set of parameters by applying a policy gradient step for a task $\mathcal M^i \sim p(\mathcal M)$:
$$\phi^i_1=f(\mathcal D^i_0,\phi_0)=\phi_0+\alpha\nabla_{\phi_0}\hat J(\mathcal D ^i_0,\pi_{\phi_0})$$
where $\hat J(\mathcal D ^i_0,\pi_{\phi_0})$ is an estimate of the returns of the policy $\pi_{\phi_0}$ for the task $\mathcal M^i$  and $\alpha$ is the learning rate. Difficult tasks may require multiple gradient steps in the inner-loop, MAML computes the gradient of the returns of the updated policy with respect to the initial parameters:
$$\phi'_0=\phi_0+\beta\nabla_{\phi_0}\sum_{\mathcal M^i\sim p(\mathcal M)} \hat J(\mathcal D ^i_0,\pi_{\phi_0})$$
where $\pi ^i_{\phi_1}$ is the policy for task $i$ updated once by the inner-loop, $\beta$ is a learning rate, and $\nabla_{\phi_0}\hat J(\mathcal D ^i_0,\pi^i_{\phi_1})$  is the gradient of the returns of the updated policy computed w.r.t. the initial policy parameters. Such a gradient through an RL inner-loop is often referred to as a meta-gradient. Descending the meta-gradient corresponds to optimizing the outer-loop objective.

# Why MAML is Model-Agnostic
Metric-based and Model-based approaches force constraints on either the sampling or the model's architecture. MAML, on the other hand requires the model to be optimizable by a gradient-based optimizer. 

The neural network is designed the same way your usual model might be. All the magic happens during optimization. As a consequence, unlike metric based and model based approaches, MAML lets you choose the model architecture freely. This has the benefit of being applicable to reinforcement learning.

# How MAML works
## Objective
The normal optimization steps for a gradient descent system can be described as 
$$\begin{align}
\min_\phi\mathcal L_\tau(\phi)\\
s.t.\; \phi\leftarrow\phi-\alpha\nabla_\phi\mathcal L_\tau(\phi)
\end{align}$$
The key idea of MAML is to mitigate the problem of this requiring many datapoints for each task $\tau$ by learning not only from the data regarding exactly our task but also from data of similar tasks. We make the additional assumption that $\tau_i\sim p(\tau)$. $\tau$ is now a random variable and $\phi_\tau$ is a set of parameters for task $\tau$. we may use different parameters for each task, use the same parameters for every task, or do something in between.

Additionally, we will not simply use the data from other tasks to find parameters that are optimal for all tasks, but keep the option to fine-tune our model, i.e., take additional optimizer steps on data from the new taks $\tau_i$. Afterward, we want to have converged to $\tau_i$ and reuse the pre-fine-tune-version of the model for each new task. Thus, we can express our optimization objective as 
$$\min_\theta\mathbb E_\tau[\mathcal L_\tau(U_\tau(\theta))]$$
where $U_\tau:\Phi\rightarrow\Phi$ is an optimization algorithm that maps $\theta$ to a new parameter vector $U_\tau(\theta)$, being the result of fine-tuning $\theta$ on data from task $\tau$, using optimizer $U_\tau$. I will be assuming that $U_\tau$ corresponds to performing gradient descent with a variable number of steps for this note.

Since $\theta$ can be seen as the initialization of the optimizer $U_\tau$ we can interpret $\theta$ as a task-level parameter; as such it acquires the status of a meta-parameter.

## Pretraining
When ignoring the optimizer $U_\tau$ we return to the standard machine learning setting. However, we are not operating on a few samples of one task but have a whole distribution of tasks at our disposal. Hence, we can reliably solve the simplified objective with gradient descent. 

Omitting the update procedure $U_\tau$, we expect the final $\theta$ to be chosen such that fine-tuning the model on only a few samples of some task $\tau_i$ from the distribution makes the model parameters close to optimal. This hope might seem naive, considering that we did not reason about why $U_\tau$ might be disregarded, but simply disregarded it. 

Expectations are commonly approximated by an empirical mean over samples from the respective distribution. If we apply this here the resulting gradient is also the empirical mean of the task gradients
$$\theta\leftarrow\theta-\frac{\alpha}{n}\nabla_\theta\sum_i\mathcal L_{\tau_i}(\theta)$$
The authors of MAML, call this type of baseline the pretrained model: we can simply pretain over all available data and defer the problem of dealing with $U_\tau$. Now, we can make use of the pretrained model by simply fine-tuning the final $\theta$, the result of our pretraining, on a new task.

## Implementing the pretrained model
Below is an implementation that is agnostic to the choice of optimizer.
``` python
import tensorflow as tf

def updatePretrained(model, optimizer, batch):
	"""Does one update step of the 'pretrained' model. Batch is a set of 
	samples from a collection of sampled tasks of the shape 
	(nTasks, nSamples), where each sample is a pair of labels and inputs.
	"""
	def taskLoss(batch):
		y_train, x_train = batch
		return mse(y_train, model(x_train)) # or cross-entropy, or ...
	
	with tf.GradientTape() as tape:	
		batchLoss = tf.map_fn(taskLoss, elems=batch, 
				      fn_output_signature=tf.float32)
		loss = tf.reduce_sum(batchLoss)

	optimizer.minimize(loss, model.trainable_weights, tape=tape)
```

In certain situation $\theta$ is either impossible or at least incredibly difficult to find. To grain some insight into the difficulties of the problem we have to revisit the original optimization objective[[Model-Agnostic Meta-Learning#Objective|written here]]. We can augment the original notation by giving $U_\tau$ a superscript such as $U^{(m)}_\tau$ to indicate that we perform $m$ steps of gradient descent. The simplified objective of the pretrained model can be received by setting $m=0$ and indicates that no fine-tuning is performed.

The loss spec for some task samples becomes:
$$\sum_i\mathcal L_\tau(\theta)$$
a simple sum of loss spaces. From now on we have to distinguish between the task loss spaces which are defined by the individual $\mathcal L_{\tau_1}, ..., \mathcal L_{\tau_n}$ for tasks $\tau_1, ...,\tau_n$ and the accumulated loss space, defined by 
$$\sum_i\mathcal L_\tau(U^{(m)}_\tau(\theta))$$
As we increase $m$, the loss space and with it the position of the minimum can change, indicating that the simplified objective of the pretrained model can be a poor approximation of the few shot meta learning objective we would like to solve. 

We will now try to optimize the previously established few-shot learning objective
$$\min_\theta\mathbb E_\tau[\mathcal L_\tau(U_\tau^{(m)}(\theta))]$$
for $m>0$. In short, MAML optimizes the same $\theta$ as the pretrained model, but in its optimization strategy, it acknowledges the effect of fine-tuning function $U_\tau$ on the accumulated loss space.

The three main steps of the method, given a meta-parameter $\theta$:
1. Sample a number of tasks $\tau_i$ from $p(\tau)$
2. For each task, obtain $\phi_i=U_{\tau_i}(\theta)$,by minimizing $\mathcal L_{\tau_{i,train}}(\theta)$ on a few training samples.
3. Update $\theta$ by gradient descent such that it minimizes $\mathcal L(\theta):=\sum_i\mathcal L_{\tau_{i,test}}(\phi_i)$ on a few test samples
Note that $\mathcal L_{\tau_{i,train}}$ and $\mathcal L_{\tau_{i,test}}$ are two instances of the same loss function on the same task $\tau_i$ and correspond to training or test data from this task (though $\tau_i$ chaneges while iterating over $i$). The easiest way to obtain $\phi_i$, is to do a single step of gradient descent ($\phi_i$ will not be optimal but most likely better then $\theta$):
$$\phi_i=\theta-\alpha\nabla_\theta\mathcal L_{\tau_{i,train}}(\theta)$$ Further, updating $\theta$ requires us to evaluate the gradient of the individual task losses on a set of test data. We obtain the gradient of the overall loss as follows:
$$\nabla_\theta\mathcal L(\theta)=\sum_i\nabla_\theta\mathcal L_{\tau_{i,test}}(\phi_i)$$
Note that $\phi_i=U_{\tau_i}(\theta)$ depends on $\theta$, which means that we have to take a gradient through the optimizer $U$. We can then update $\theta$ via gradient descent, using a new learning rate $\beta$:
$$\theta\leftarrow\theta-\beta\nabla_\theta\mathcal L(\theta)$$

----
## Reference
[[@finnModelAgnosticMetaLearningFast2017]]
https://interactive-maml.github.io

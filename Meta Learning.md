---
tags:
- programming/machine-learning/meta-learning
- ruff-note
- research/paper-notes
---
Meta-learning is commonly understood as learning to learn, which refers to the process of improving a learning algorithm over multiple learning episodes. In contrast, conventional ML improves model predictions over multiple data instances.

During base learning an inner or lower/base learning algorithm solves a task such as image classification, defined by a dataset and objective. During meta-learning, an outer or upper/meta algorithm updates the inner learning algorithm such that the model it learns improves an outer objective.

The essential characteristic of contemporary neural-network  meta-learning is an explicitly defined meta-level objective, and end-to-end optimization of the inner algorithm with respect to this  objective.

# Formalization
## Conventional Machine Learning
We are given a training dataset $\mathcal D=\{(x_1,y_1),...,(x_n,y_n)\}$, on which we  can train a predictive model $\hat{y} = f_\theta(x)$ parameterized by $\theta$ by solving:
$$\theta^*=\arg\min_\theta\mathcal L(D;\theta,\omega)$$
where $\mathcal L$ is a loss function that measures the error between true labels and those predicted by $f_\theta(\cdot)$. The conditioning on $\omega$ denotes the dependence of this solution on assumptions about 'how to learn' such as the choice of optimizer for $\theta$. Generalization is then measured by evaluating a number of test points with known labels.
## Task-Distributed View
WE can evaluate the performance of $\omega$  over a distribution of tasks $p(\mathcal T)$. Here we loosely define a task to be a dataset and a loss function $\mathcal T=\{\mathcal D,\mathcal L\}$. Learning how to learn thus becomes $$\min_\omega\underset{\mathcal T\sim p(\mathcal T)}{\mathbb E}\mathcal L(\mathcal D;\omega)$$
where $\mathcal L(\mathcal D;\omega)$ measures the performance of a model trained using $\omega$ on dataset $\mathcal D$. 'How to learn', i.e. $\omega$, is often referred to as across-task knowledge.

### Meta-Training
We denote the set of $M$ source tasks used in the meta-training stage as $\mathfrak D_{\text{source}}=\{(\mathcal D_{\text{source}}^{\text{train}}\mathcal D_{\text{source}}^\text{val})^{(i)}\}^M_{i=1}$ where each task has both training and validation data. Often, the source train and validation data. The meta-training steo if learning how to learn can be written as:
$$\omega^*=\arg\max_\omega\log p(\omega|\mathfrak D_\text{source})$$ 
### Meta-Testing
Now we denote the set of $Q$ target tasks used in the meta-testing stage as $\mathfrak D_{\text{target}}=\{(\mathcal D_{\text{target}}^{\text{train}}\mathcal D_{\text{target}}^\text{val})^{(i)}\}^Q_{i=1}$ where each task has both training and test data. In the meta-testing stage we use the learned meta-knowledge $\omega^*$ to train the abse model on each previously unseen target task $i$:
$$\theta^{*\ (i)}=\arg\max_\theta\log p(\theta|\omega^*,\mathcal D_\text{target}^{\text{train}\ (i)})$$
### Meta under-/overfitting
Meta overfitting is an issue whereby the meta knowledge learned on the source tasks does not generalize to the target tasks. It is relatively common, especially in the case where only a small number of source tasks are available. It can be seen as learning an inductive bias $\omega$ that constrains the hypothesis space of $\theta$ too tightly around solutions to the source tasks

## Bilevel Optimization View
The task distributed view does not specify how to solve the [[Meta Learning#Meta-Training|meta training]] step. This is commonly done by casting as a [[Bilevel Optimization|bilevel optimization]] problem. 
$$\begin{align}
\omega^* &=\underset{\omega}{\arg\min}\sum^M_{i=1}\mathcal L^\text{meta}(\theta^{*\ (i)}(\omega),\omega,\mathcal D^{\text{val}\ (i)}_\text{source})\\
\text{s.t.}\; \theta^{*\ (i)} (\omega) &= \underset{\theta}{\arg\min}\ \mathcal L^\text{task}(\theta,\omega,
\mathcal D^{\text{train}\ (i)}_\text{source})
\end{align}$$
where $\mathcal L^\text{meta}$ and $\mathcal L^\text{task}$ refer to the outer and inner objectives respectively.

## Feed-Forward Model View
It can be helpful to understand this family of approaches to instantiate the abstract objective of the [[Meta Learning#Task-Distributed View|task distributed view]] as a meta training linear regression toy example. 
$$\min_\omega\underset{\underset{(\mathcal D^\text{tr},\mathcal D^\text{val})\in \mathcal T}{\mathcal T\sim p(\mathcal T)}}{\mathbb E}\sum_{(x,y)\in D^{val}}\left[(x^Tg_\omega(\mathcal D^\text{tr})-y)^2\right]$$
Here we meta-train by optimizing over a distribution of tasks. For each task a train and validation set is drawn. The train set $\mathcal D^\text{tr}$ is embedded into a vector $g_\omega$ which defines the linear regression weights 

![[Pasted image 20230711112510.png]]
## Metric-Based Approaches
The core idea of metric based approaches is to compare two samples in a latent(metric) space: In this space, samples of the same class are supposed to be close to each other, while tow samples from different classes are supposed to have a large distance.

## Model Based Approaches
Model-based approaches are neural architectures that are deliberately designed for fast adaption to new tasks without an inclination to overfit. 

## Optimization Based approach
----
## Reference

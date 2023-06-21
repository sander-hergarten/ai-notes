Dreamer V3 is a model based rl method that creates a world model for higher sample eficiency. The Dreamer V3 Model consists of 3 Models:
- World Model
- Actor
- Critic
These are trained concurrently from replayed experience without sharing gradients. Every Network has its own loss function.

One goal of Dreamer V3 is to be able to optimization accross differnet domains with fixed hyperparameters. To solve the Problem of diferent magnitudes of rewards, actions and prediction environments the Authors present a Transformation:

# Symlog Predictions
The Problem that Symlog Predictions try to solve is that when confronted with a large variety of differently scaled predictions no loss function exists that would work accross large and small values. Normalizing values introduces "non-stationarity" into the optimization. 

The symlog prediction works by modifiying the loss function so the networks tries to return the $symlog()$ of the output instead of the output directly. To recieve the correct output the networks output is then given to the inverse $symexp()$ function.
$$\begin{align}
&& L(\theta) = \frac{1}{2}( f(x, \theta),- symlog(y))^2
&& \hat{y} = symexp(f(x, \theta))
\end{align}$$
$symlog()$ and $symexp()$ are defined as:
$$\begin{align}
&& symlog(x)= sign(x)ln(\rvert x\lvert +1)
&& symexp(x)= sign(x)(exp(\rvert x\lvert) -1)
\end{align}$$

This function was chosen such that it mimics the identity function around $x=0$ and the natural logarithm against $\inf$. This causes large values to still easily be learned even when parameters where optimized for smaller values

# World Model
The Worlf Model attempts to imitate the environment by prediction of the next steps returns and observations when given a certain action and trajectory. The Authors use a Recurrent neural network that consists of 3 parts:
1. Sequence Model 
2. Encoder
3. Dynamics predictor

In addition  3 more subnetworks are part of the World Model:
4. Reward predictor
5. Continue predictor
6. Decoder

### Encoder
$$z_t \sim q_{\phi}(z_t\ |\ h_t,\ x_t)$$
The Encoder creates the stochastic latent representation of the observation. $z_t$. It recieves the recurrent deterministic state and returns a distribution of 32x32 logits. To those logits a random vector is mixed in a $0.99|0.01$ ratio. A value is sampled from the vector to create a 32x1 vector which then is onehot encoded to the 32x32 representation.

### Sequence Model
$$h_t = f_{\phi}(h_{t-1},\ z_{t-1},\ a_{t-1})$$
The sequence Model predicts the sequence of these representations given past actions and model state.

### Dynamics Predictor 
$$\hat{z}_t \sim p_{\phi}(\hat{z}_t\ |\ h_t)$$
The Dynamics predictor takes a recurrent state $h_t$ and tries to predict the latent state $z_t$. Its output is $\hat{z}_t$  

### Reward / Continue Predictor 
The reward and continue predictor take the current recurrent state $h_t$ and latent state $z_t$ to predict the reward or if an episode will continue at $t$.

The Continue Predictor is trained with binary classification loss 

The Reward Predictor is trained using the symlog loss to account for large variances in rewards 

### Decoder
$$\hat{x}_t \sim p_{\phi} (\hat{x}_t\ | \ h_t,\ z_t)$$
The decoder is the counter part  of the encoder and will decode the current observation out of the latent and recurrent state $h_t,\ z_t$

The decoder is trained using the symlog loss 


## Losses 
The gradients are pulled end to end to minimize the prediction loss, the dynamics loss , and the representation loss. The final loss function is weighted as $\beta_{pred}=1,\beta_{dyn}=0.5,\beta_{rep}=0.1$

$$\mathcal{L}(\phi)=E_{q_{\phi}}\Lbrack{\sum}\Rbrack$$

### Prediction Loss
The prediction loss trains the decoder and reward predictor via the symlog loss and the continue predictor via binary classification loss.
$$\mathcal{L}_{pred}(\phi) = -\ln{p_{\phi}()}$$

### Dynamics Loss
The dynamics loss trains the sequence model to predict the stochastic representation by minimizing the KL divergence between the predictor and the next stochastic representation

### Representation Loss
The representation loss trains the representation to become more predictable if the dynamics cannot predict their distribution allowins to.


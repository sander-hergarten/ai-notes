Given a sequence $x=(x_1,x_2,...,x_T)$, the RNN updates its recurrent hidden state $h_t$ by 
$$h_t=\begin{cases}0\quad\quad\quad\quad\quad t=0\\ \phi(h_{t-1}, x_t),\ \text{otherwise}\end{cases}$$
where $\phi$ is a nonlinear function.

## Traditional Recurrent units
The update of the recurrent hidden state is implemented as 
$$h_t=g(Wx_t+Uh_{t-1})$$
where g is a smooth bounded function such as a logistic function or a hyperbolic tangent function

## Generative RNNs
A generative RNN outputs a probability distribution over the next element of the sequence, given its current state $h_t$, and this generative model can capture a distribution over sequences of variable length by using a special output symbol to represent end of sequence. The sequence probability can be decomposed into 
$$\mathbb P(x_1,...,x_T)=\mathbb P(x_1)\mathbb P(x_2|x_1)\mathbb ...\mathbb P(x_T|x_1,...,x_{T-1})$$
where the last element is a special end-of-sequence value. We model each conditional probability distribution with 
$$\mathbb P(x_t|x_1,...,x_{t-1})=g(h_t)$$
where $h_t$ is the hidden state. 


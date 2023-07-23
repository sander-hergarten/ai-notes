---
tags:
- programming/machine-learning/natural-language-processing
alias:
- GRU
- gru
- gated recurrent unit
---
GRU aims to solve the vanishing gradient problem which comes with a standard recurrent neural network. GRU can also be considered as a variation on the LSTM because both are designed similarly and, in some cases, produce equally excellent results. 

# How do GRUs work
TO solve the vanishing gradient problem of a standard RNN, GRU uses update gate and reset gate. Basically these are two vector which decide what information should be passed to the output. THe special thing about them is that they can be trained to keep information form long ago

![[Pasted image 20230713180111.png]]
First let's introduce the notations
![[Pasted image 20230713180800.png]]
(plus operation, sigmoid function, Hadamard product)

## Update Gate
We start with calculating the update gate $z_t$ for time step $t$ using the formula:
$$z_t=\sigma(W^{(z)}x_t+U^{(z)}h_{t-1}$$
when $x_t$ is plugged into the network unit, it is multiplied by its own weight $W(z)$. The same goes for $h_{t-1}$ which holds the information for the previous $t-1$ units and is multiplied by its own weight $U(z)$. Both results are added together and a sigmoid activation function is applied to squash the results between 0 and 1. Following the above schema we have:
![[Pasted image 20230713204050.png]]
The update gate helps the model determine how much of the past information needs to be passed along to the future. That is really powerful because the model can decide to copy all the information from the past and eliminate the risk of vanishing gradient problem. 

## Reset Gate
This gate is used from the model to decide how much of the past information to forget. To calculate it, we use:
$$r_t=\sigma(W^{(r)}x_t+U^{(r)}h_{t-1}$$
This formula is the same as the one for the update gate. The difference comes in the weights and the gates usage.
![[Pasted image 20230713204459.png]]

## Current Memory Content
To see how the gates will affect the final output, first we start with the usage of the reset gate. We introduce a new memory content which will use the reset gate to store the relevant information from the past. It is calculated as follows:
$$h_t'=\tanh(Wx_t+r_t\odot Uh_{t-1})$$
![[Pasted image 20230713205303.png]]
As the last step, the network needs to calculate 

## Final Memory at Current Time Step
As the last step, the network needs to calculate $h_t$ In order to do that the update gate is needed. It determines what to collect from the current memory content $h_{t-1}$. That is done as follows:
$$h_t=z_t\odot h_{t-1}+(1-z_t)\odot h_t$$
1. Apply element-wise multiplication to the update gate $z_t$ and $h_{t-1}$ 
2. Apply element-wise multiplication to $(1-z_t)$ and $h'_t$ 
3. Sum the results from step 1 and 2
![[Pasted image 20230713212357.png]]

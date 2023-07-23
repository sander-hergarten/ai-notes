---
tags:
- research/paper-notes
- ruff-note
---
Source: [[1412.3555.pdf]]

Almost no recent successes have been made with vanilla recurrent neural networks. More sophisticated recurrent units where used. In particular The [[LSTM]] unit and the [[Gated Recurrent Units|GRU]]. 

These units are evaluated on three polyphonic music datasets.

Unfortunately it has been observed that it is difficult to train RNNs to capture long-term dependencies because the gradients tend to either vanish or explode. This makes the gradient-based optimization method struggle, not just because of the variations in gradient magnitudes but because of the effect of short-term dependencies "hiding" long-term dependencies 

There have been two approaches to this problem:

One such approach is to devise a better learning algorithm than a simple Stochastic Gradient Descent such as the Clipped graidient.

The other approach is to design a more sophisticated activation function.
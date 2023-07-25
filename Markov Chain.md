---
tags:
- math/statistics
- math/graph-theory
---
Markov chains are a type of Markov model and as such fullfill the [[Markov Properties]]. They are a graph that can predict the likelihood to land in an absorbing state while performing a [[Directed Graphs#Walks|random walk]].

In particular Markov chains are a simplified [[Markov Decision Process]]

a Markov Chain can be described using a [[Directed Graphs|directed graph]] for example:
```mermaid
flowchart LR
 a((0))--0.1-->b((1))
 a--0.9-->c(((2)))
 c--0.1-->c
 c--0.5-->b
 c--0.1-->a
 b--0.8-->b
 b--0.2-->a
```
---
## Reference


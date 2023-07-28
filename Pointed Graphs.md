---
tags:
- math/graph-theory
aliases:
- rooted graphs
- rooted graph
- pointed graph
- accessible pointed graphs
- apg
- APG
- 
---
A Pointed Graph is a type of [[Directed Graphs|directed graph]] together with a distinguished node called its point. 

A pointed graph is Accessible if for every node $n$ there is a path from the point $n_0$ to the node $n$. If this path is always unique and non-cyclical then the pointed graph is a [[Trees|tree]] and the point is the Root of the tree. 


For example the picture of 3
![[Pasted image 20230724195700.png]]
The node labelled $0$ has no children and hence must be assigned the empty set, i.e. $0$, in any decoration. The central node has as only child the node labelled $0$. Hence in any decoration the central node must be assigned the set $\set{0}$, i.e. 1. Continuing this way we are inevitably led to the above decoration, and this decoration shows us that we have a picture of 3.

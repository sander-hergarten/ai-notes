---
tags:
- 
aliases:
- system
---
A system is an expansion of the notion of a graph so as to allow there to be a proper class of nodes. A System is a class $M$ of nodes together with a [[Classes|class]] of Edges consisting of ordered pairs of nodes. A System is a class $M$ of nodes together with a class of Edges consisting of ordered pairs of nodes.

We shall simply use $M$ to refer to the system and write that $a\rightarrow b$ in $M$ or simply $a\rightarrow b$ if $(a,b)$ is an edge of $M$.

A system $M$ is required to satisfy the condition that for each node $a$ the class $a_{M}=\set{b\in M|a\rightarrow b}$ of children of $a$ is a set

Note that a graph is simply a small system. An example of a large system is the universe $V$ with $a\rightarrow b$ whenever $b\in a$

The notion of a decoration of a graph extends to systems in the obvious way. We get the following strengthening of AFA.

----
## References
[[@aczelNonwellfoundedSets1988]]
---
tags:
- math/graph-theory
---
A forest is a graph that contains no cycles, and a connected forest is a tree. Trees and forests are simple graphs and any two vertices are connected by a unique path.
> [!info] Properties
> Let $T$ be a graph with $n$ vertices. Then the following statements are equivalent:
> 1. $T$ is a tree
> 2. $T$ contains no cycles, and has n-1 edges
> 3. $T$ is connected, and has n-1 edges
> 4. $T$ is connected, and each edge is a bridge
> 5. any two vertices of $T$ are connected by exactly one path
> 6. $T$ contains no cycles, but the addition of any new edge creates exactly one cycle

as such if $G$ is a forrest with $n$ vertices and $k$ components, then $G$ has $n-k$ edges.

## Spanning-Forrests, -Trees
Given any connected graph $G$, we can choose a cycle and remove any one of its edges, and the resulting graph remains connected. We repeat this procedure with one of the remaining cycles, continuing until there are no cycles left. The graph that remains is a tree that connects all the vertices of $G$. The resulting tree is called a spanning tree of $G$

More generally if $G$ is an arbitrary graph with $n$ vertices, $m$ edges and $k$ components, then we can carry out this procedure on each component of $G$. The result is called a Spanning Forest. 

The total number of edges removed is called the **cycle rank** of $G$ denoted by $\gamma(G)$. Note that $\gamma(G)=m-n+k$, which is a non-negative integer.

It is convenient to also define the cutset rank of $G$ to be the number of edges in a spanning forest, denoted by $\xi(G)=n-k$. 

We can derive few simple results concerning spanning forests:
>[!info]
>If $T$ is any spanning forest of a graph $G$ where the complement is defined as $$\bar{T}=(V(G), E(G)-E(T))$$, then
>1. each cutset of $G$ has an edge in common with $T$
>2. each cycle of $G$ has an edge in common with $\bar{T}$

### Fundamental set of cycles
If $T$ is a spanning forest of $G$ and we add to $T$ any edge of $G$ not contained in $T$, then we obtain a unique cycle. The set of all cycles formed in this way by adding separately each edge of $G$ not contained in $T$, is the fundamental set of cycles associated with $T$. Sometime we are not interested in the particular spanning forest chosen, and refer simply to a fundamental set of cycles of $G$. The number of fundamental cycles must be equal to the cycle rank of $G$.

TODO:
Fundamental set of cutsets








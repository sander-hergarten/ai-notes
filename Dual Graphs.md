Given a plane drawing of a planar graph $G$, we construct another graph $G^*$ called the geometric dual of $G$. The construction is in two stages:
1. inside each face $f$ of $G$ we choose a point $v^*$. these points are the vertices of $G^*$
2. corresponding to each edge $e$ of $G$ we draw a line $e^*$ that exclusively crosses $e$ and joins the vertices $v*$ in the faces $f$ adjoining $e$ these lines are the edges of $G^*$
![[Pasted image 20230618112748.png]]
($G$: black circle | $G^*$: white square)

Any two Graphs formed out of a graph $G$ this way have to be isomorphic. On the other hand if $G$ is isomorphic to $H$, it does not necessarily follow that $G^*$ is isomorphic to $H^*$. 

## Isomorphism
Creating the dual graph $G^{**}$ of the dual graph $G^*$ creates a graph isomorphic to the original graph $G$.  If $G$ is isomorphic to $H$, it does not necessarily follow that $G^*$ is isomorphic.

If $G$ is a planar graph, then a dual of $G$ can be defined by taking any plane drawing and forming its geometric dual. Since duals have been defined only for planar graphs, it is trivially true to say that a graph is planar if and only if it has a dual.

> [!quote] Theorem
> Let G be a planar graph and let $G^*$ be a geometric dual of $G$. then a set of edges in $G$ forms a cycle in $G$ if and only if the corresponding set of edges of $G^*$ forms a cutset in $G^*$
> 
> As such a set of edges of $G$ forms a cutrset in $G$ if and only if the corresponding set of edges of $G^*$ forms a cycle in $G^*$

## Abstract Dual
We say that a graph is an abstract dual of a graph $G$ if there is a one-one correspondence between the edges of $G$ and those of $G^*$, with the property that a set of edges of $G$ forms a cycle in $G$ if and only if the corresponding set of edges of $G^*$ forms a cutset in $G^*$.  as such the concept of an abstract dual generalizes the geometric dual, in the sense that if $G$ is a plane graph and $G^*$ is a geometric dual of $G$ then $G^*$ is an abstract dual of $G$. 

We can derive:
> [!quote] Theorem 
> if $G^*$ is an abstract dual of $G$, then $G$ is an abstract dual of $G^*$
> 
> A Graph is planar if and only if it has an abstract dual









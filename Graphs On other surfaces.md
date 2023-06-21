It is easy to see that $K_5$ and $K_{3,3}$ can be drawn without crossings on the surface of a torus, and it is natural to ask whether there are analogues of [[Planarity#Euler's Formula|Euler's formula]] and [[Planarity#Kuratowski's Theorem|Kuratowski's theorem]] for graphs drawn on such surfaces. The torus can be thought of as a sphere with  one handle. 

## Graph genus
More generally a surface is of genus $g$ if it is topologically homeomorphic to a sphere with $g$ handles. Thus the genus of a sphere is 0, and that of a torus is 1. 

A graph that can be drawn without crossings on a surface of genus $g$ but not on one of genus $g-1$, is a graph of genus $g$. Thus $K_5$ and $K_{3,3}$ are graphs of genus 1 (also called toroidal graphs)

One constraint to the genus of a graph is that it does not exceed the crossing number.

## Kuratowski's theorem analogue
There is currently no complete analogue of Kuratowski's theorem for surfaces of genus $g$, although there have been proofs for the existence of a finite collection of 'forbidden' subgraphs of genus $g$, for each value of $g$, corresponding to the forbidden subgraphs $K_5$ and $K_{3,3}$ for graphs of genus 0

## Euler's formula analogue
There exists a natural generalisation for graphs of genus $g$. In this generalisation, a face of a graph of genus $g$ is defined in the obvious way
> [!quote] Theorem 
> Let G be a connected graph of genus $g$ with $n$ vertices, $m$ edges and $f$ faces. Then $$n-m+f=2-2g$$

Form this we can derive following corollary:
> [!quote] Theorem 
> The genus $g(G)$ of a simple graph $G$ with $n \ge 4$ vertices and $m$ edges satisfies the inequality:$$g(G)\ge\left\lceil \frac{m-3n}{6}+1\right\rceil$$

## Thickness
Just as for the thickness of a graph, little is known about the genus of an arbitrary graph. The usual approach is to the above theorem to obtain a lower bound for the genus, and then to try to obtain the required the required drawing by direct construction.

> [!quote] Theorem
> $$g(K_n)=\left\lceil\frac{(n-3)(n-2)}{12}\right\rceil$$


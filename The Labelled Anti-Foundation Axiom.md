---
tags:
- math/set-theory
---
The Labelled Anti-Foundation Axiom uses [[labelled graphs]] and labelled decoration.

> [!Abstract] The Labelled Anti-Foundation Axiom
> Every labelled graph has a unique labelled decoration.

The ordinary anti-foundation axiom may be viewed as a special case by treating ordinary graphs as labelled graphs with an empty set of labels attached

Given sets $a_{0}, a_{1},...$ we can obtain the sets $x_n$ such that $x_n=(a_n,x_{n+1})$ for $n=0,1,...$ in the following way:

Consider the labelled graph having natural numbers as nodes, an edge $n\rightarrow n+1$ for each $n$ and sets of labels given by:

$$\begin{align}
(2n)\downarrow &=\set{\set{a_n}}\\
(2n+1)\downarrow &=\set{a_n}
\end{align}$$
Using the labelled anti foundation axiom let $d$ be the unique labelled decoration of the labelled graph.

Then for $n=0,1,...$ 
$$\begin{align}
d(2n)&=\set{d(2n+1)}\, \cup\, \set{\set{a_n}}\\
d(2n+1)&=\set{d(2n+2)}\,\cup\,\set{a_n}\\
\end{align}$$
Hence if $x_n=d(2n)$ then 
$$\begin{align*}
x_n&=\set{d(2n+1),\set{a_n}}\\
&= \set{\set{x_{n+1},a_n},\set{a_n}}\\
&= (a_n,x_{n+1})
\end{align*}$$
for each $n$. Hence we have obtained the desired sets $x_n$.

We can expand this concept even more if we consider that we are working with systems of equations and how these can be solved in a unique fashion. If we us a formulation that shows that every system of equations of a certain type has a unique solution we can simply apply this result directly to each example.

In order to formulate the lemma in an intuitively appealing way we need to consider an expansion of the universe of [[Pure Sets|pure sets]]. The expansion of the universe involves the addition of [[Atoms|atoms]], and creates [[Impure Atom Sets]]


----
## References
[[@aczelNonwellfoundedSets1988]]

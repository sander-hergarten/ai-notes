---
tags:
- math/set-theory
---
When creating the [[Pictures]] of a set we call the resulting graph Well-founded if it has no infinite path.
> [!quote] Mostowski's Collapsing Lemma
> Every well-founded graph has a unique decoration.

This Result is proved by a simple application of definition by recursion on a well-founded relation to obtain the unique function $d$ defined so that 
$$dn=\set{dn'|n\rightarrow n'}$$
for each node $n$ of the graph. The decoration $d$ assigns the set $dn$ to the node $n$. Note the obvious consequence.
> [!quote] Corollary
> Every well-founded apg is a picture of a unique set.

All sets have a picture as well.

To see this we will associate with each set $a$ its canonical picture. Form the graph that has its nodes those sets that occur in sequence $a_0,a_1,...$ such that 
$$...\in a_2\in a_1\in a_0=a$$
and having as edges those pairs of nodes $(x,y)$ such that $y\in x$. If $a$ is chosen as the point we obtain an apg. This apg is clearly a picture of $a$, the decoration consisting of the assignment of the set $x$ to each node $x$. Note that this construction does not require the set $a$ to be well-founded.

Every picture of a set can be unfolded into a tree picture of the same set Given an apg we mau form the tree whose nodes are the finite paths of the apg that start from the point of the apg and whose edges are pairs of paths.

The root of this tree is the path $a_0$ of length one. This tree is the Unfolding of the apg. Any decorations of the apg induces a decoration of its unfolding by assigning to the node $a_0\rightarrow ...\rightarrow a$ of the tree the set that is assigned to the node $a$ of the apg by the decoration of the apg.
The unfolding of the canonical picture of a set will be called the canoncal tree picture of the set.

> [!abstract] The Anti-Foundation Axiom (AFA):
> Every graph has a unique decoration

Note the following consequences:
- Every apg is a picture of a unique set.
- non-well-founded sets exist.
In fact any non-well-founded apg will have to picture a non-well-founded set.

The AFA can further be strengthened by introducing the [[The Labelled Anti-Foundation Axiom]]


## Atoms
Atoms are objects that are not sets and are not made up of sets in any way, so that they habe no set theoretical structure. But they can be used in the formation of sets.

The construction of an expanded universe by adjoining to a universe of sets, atoms and adding all the sets that can involve these atoms in their build up is analogous to the construction of a polynomial ring from a ring by adjoining indeterminates and adding all the polynomials in those indeterminates with coefficients taken from the ring. 

We assume that for each pure set $i$  there is an atom $x_i$, with $x_i \ne x_j$ for distinct pure sets $i,j$. If $X$ is a class of atoms then we call sets that may involve atoms from the class $X$ in their build up $X$-sets. The solution lemma will apply to asystem of equations of the form 
$$x=a_x \quad (x\in X)$$
where $a_x$ is an $X$-set for each $x \in X$. For example given pure sets $a_0,a_1,...$ the system of equations $$x_n=(a_n,x_{n+1})\quad (n=0,1,...)$$
Has the above form when we take $X=\set{x_0,x_1,...}$ and for each $n$ we take $a_{x_n}$ to be $(a_n,x_{n+1})$; i.e. the $X$-set $\set{\set{a_n},\set{a_n,x_{n+1}}}$. In this example it is clear what a solution of this system of equations must be. It is a family of pure sets $b_0,b_1,...$, one for each atom in $X$, such that 
$$b_n=(a_n,b_{n+1}\;\text{for $n=0,1,...$})$$
notice that the right hand sides of these equations are obtained from the right hand sides of the orignial systme of equations by substituting $b_n$ for each atom $x_n$
---
title: Non-well-founded sets
authors: Peter Aczel
year: 1988
---

# Introduction
A non-well-founded set is an extraordinary set in the sense of Mirimanoff. Such as set has an infinite descending membership sequence; i.e. an infinite sequence of sets, consisting of an element of the set, an element of that element, an element of that element of that element and so on.

What is extraordinary about such a set is that it would seem that it could never get formed. for in order to form the set we would first have to form its elements, and to form those elements we would have to have previously formed their elements and so on leading to an infinite regress. Of course this anthropomorphic manner of speaking about the formation of sets is only that; a manner of speaking. We humans do not actually physically form sets out of their elements, as sets are abstract objects. 

Nevertheless the sets that have been needed to represent the standard abstract objects of modern mathematics have in fact been the ordinary well-founded ones. This observation has been institutionalised in the standard axiom system *ZFC* of axiomatic set theory, which includes among its axioms the foundation axiom ***FA***. This axiom simply expresses that all sets are well-founded.

If non-well-founded  sets are not needed for the development of mathematics then it may well seem natural to leave them out of consideration when formulating an axiomatic basis for mathematics. 

Sometimes a stronger view is expressed. According to that view there is only one sensible coherent notion of set. That is the iterative conception in which sets are arranged in levels, with the elements of a set placed at lower levels than the set itself. For the iterative conception only well-founded sets exist and FA and the other axioms of ZFC are true when interpreted in the iterative universe of pure sets. 

There has been yet one more reason why FA has been routinely included among the axioms of axiomatic set theory. This is the fact that the cumulative hierarchy of the iterative universe has an enticingly elegant mathematical structure.

This structure was already revealed by Mirimanoff and over the years it has been powerfully exploited by set theorists in a great variety of model constructions. There is a natural reluctance to forgo the pleasure of working within this structure. 

It turns out that other approaches can be treated in a uniform manner and this leads to the formulation of an axiom AFA$^\sim$ relative to the definition of a suitable relation $\sim$ to express the criterion of set equality. The suitable relations $\sim$ are called regular bisimulation relations and range between two possible extremes:
1. The maximal bisimulation relation on the univere of sets. This relation gives the most generous criterion for set equality which roughly states that sets are equal whenever possible keeping in mind that if two sets are equal then any element of one set must be equal to an element of the other set. It is this relation that gives rise to the axiom AFA. 
2. The other extreme of a strengthening is of the extensionality criterion for set equality which roughly states that two sets are equal if they are isomorphic in a suitable sense. This gives rise to yet another anti foundation axiom that we call FAFA. It turns out that there is an alternative notion of isomorphism between sets which gives rise to yet another anti foundation axiom which we call SAFA

In all we consider the four specific anti-foundation axioms AFA, BAFA, FAFA and SAFA. Each can be consistently added to the axiom system ZFC$^-$ and each gives rise to an axiom system in which every possible non-well-founded set exists when account is taken of the particular criterion of set equality.that is being used.

# Part One
## Chapter 1
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

In order to formulate a lemma called the solution lemma in an intuitively appealing way we need to consider an expansion of the universe of [[Pure Sets|pure sets]]. The expansion of the universe involves the addition of [[Atoms|atoms]], and creates [[Impure Atom Sets]].

The solution lemma will apply to a system of equations of the form 
$$x=a_{x}\quad (x\in X)$$
where $a_x$ is an $X$-set for each $x\in X$. For example given pure sets $a_0,a_1,...$ the system of equations
$$x_n=(a_n,x_{n+1})\quad n=0,1,...$$
has the above form when we take $X=\set{x_0,x_1,...}$ and for each $n$ we take $a_{x_n}$ to be $(a_{n},x_{n+1})$ i.e. the $X$-set $\set{\set{a_n},\set{a_n,x_{n+1}}}$. In this example it is clear what a solution of this system of equations must be. It is a family of pure sets $b_0,b_1,...$ one for each atom in $X$, such that 
$$b_n=(a_n,b_{n+1})\text{ for $n=0,1, ...$}$$
Notice that the right hand sides of these equations are obtained from the right hand sides of the original system of equations by substituting $b_n$ for each atom $x_n$. This suggests what a solution to the general system of equations should be. 

It should be a family $\pi=(b_{x})_{x\in X}$ of pure sets $b_x$, one for each $x \in X$, such that for each $x\in X$ 
$$b_{x} =\hat\pi a_{x}$$
Here, for each $X$-set $a$, the set $\hat\pi a$ is that pure set that is obtained from $a$ by substituting $b_x$ for each occurrence of an atom $x$ in the build up of $a$.

So $\hat\pi$ is the substitution operation characterised in the following result.

> [!Abstract] Substitution Lemma
> For each family of pure set $\pi=(b_{x})_{x\in X}$ there is a unique operation $\hat\pi$ that assigns a pure set $\hat\pi a$ to each $X$-set a such that $$\hat\pi a\quad=\quad \set{\hat\pi b| \text{ $b$ is an $X$-set such that $b\in a$}}\;\cup\;\set{\pi x|x\in a\cap X}$$

We can now state the result we have been aiming at

>[!abstract] Solution Lemma
>If $a_x$ is an $X$-set for each atom $x$ in the class $X$ of atoms then the system of equations
>$$x=a_{x}\quad (x\in X)$$
>has a unique solution; i.e. a unique family of pure sets $\pi=(b_x)_{x\in X}$ such that for each $x\in X$
>$$b_{x}=\hat\pi a_x$$ 

Using these systems we can strengthen the AFA even further 
> [!abstract] Assuming AFA
> Each system has a unique decoration

We can prove this 
## Chapter 2


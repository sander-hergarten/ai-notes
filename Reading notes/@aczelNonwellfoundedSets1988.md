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
The Anti foundation axiom is obviously equivalent to the conjunction of the following two statements
- AFA$_1$: Every graph has at least one decoration
- AFA$_2$: Every graph has at most one decoration 

In this chapter we shall give equivalent formulations.

The extensionality criterion says that two sets are equal if they have the same elements. For well-founded sets no more can be said about equality. The extensionality axiom does not answer the question of set equality for non-well-founded sets. While the AFA implies that there is at most one solution to the equation, it is in fact consistent to suppose that there are many solutions. 

We can however easily show through AFA$_2$ $a\equiv b\Rightarrow a=b$ where  $\equiv$ means that $a$ and $b$ share the same apg. 

## Bisimulation
We can define a binary relation $R$, such as $\equiv$, on the system $M$ and we call this a bisimulation on $M$ if $R\subseteq R^+$, where for $a,b\in M$:
$$\begin{align}
aR^{+}b \Longleftrightarrow\\
\text{for all $x\in a_M$ there exists $y\in b_M$ so that $xRy$}\\
\text{and for all $y\in a_M$ there exists $x\in b_M$ so that $xRy$}
\end{align}$$
In general a system $M$ will have many bisimulations. We will see that $\equiv$ is the maximum bisimulation on the system $V$. A maximum bisimulation exists on any system.

> [!abstract] Theorem
> There is a unique maximum bisimulation $\equiv_M$ on each system $M$; i.e.
> 1. $\equiv_M$ is a bisimulation on $M$
> 2. If $R$ is a bisimulation on $M$ then for all $a,b\in M$ $$aRb\Longrightarrow  a\equiv_{M}b$$ In fact $$a\equiv_M\Longleftrightarrow aRb\text{ for some small bisimulation $R$ on $M$}$$ The relation $\equiv_M$ is also sometimes called the weakest bisimulation or largest bisimulation on $M$

> [!Tip] Proposition 2.5
> For all sets $a,b$
> $$a\equiv b\Longleftrightarrow a\equiv_{V}b$$ 
> or written out: if there exists a bisimulation that contains $a,b$ then $a,b$ is contained in the maximum bisimulation. And if $a,b$ exist in the maximum bisimulation there exists a bisimulation that constians $a,b$
> 

^9ee65d

We can show that this is true: As $\equiv$ is a bisimulation on $V$, and $\equiv_V$ is the maximum bisimulation on $V$ it follows that the implication from left to right hols. 

For the converse implication it suffices to show that if $R$ is a bisimulation on $V$ then for all sets a,b
$$aRb\Longrightarrow a\equiv b$$
So let $R$ be a bisimulation on $V$. 
Define the system $M_0$ as follows. The nodes of $M_0$ are the elements of $R$; i.e. the ordered pairs $(a,b)$ such that $aRb$. The edges of $M_0$ are defined so that 
$$(a,b)\rightarrow(x,y)\text{ in $M_0$}\Longleftrightarrow x\in a\quad\&\quad y\in b$$Now observe that $d_{1},d_2$ are both decorations of $M_0$, where for $(a,b)\in M_0$ 



Some more properties:
1. For all $a,b\in M$ $$a=_M^{+}b\Longleftrightarrow a_M=b_M$$
2. If $R \subseteq M\times M$ then $$(R^{-1})^{+}=(R^+)^{-1}$$
3. If $R_1,R_{2}\subseteq M\times M$ then $$R_{1}^{+} |R^{+}_{2}\subseteq (R_{1}|R_{2})^{+}$$
> [!tip] Proposition 2.7
> For each system $M$ the relation $\equiv_M$ is an equivalence relation on $M$ such that for all $a,b\in M$$$a\equiv^{+}_{M}b\Longleftrightarrow a\equiv_{M}b$$ 

As $\equiv_{M}$ is a bisimulation we have the implication from right to left. As the operation $(\ )^+$ is monotone it follows that $\equiv_{M}^{+}$ is also a bisimulation. and since $\equiv_M$ is the maximum bisimulation $\equiv_M^+$ is the same bisimiulation.

If $M$ is a system we can show that for all $a,b\in M$ ^d4fd80
1. $a_M=b_{M}\Longrightarrow a\equiv_{M}b$
2. $Ma\cong Mb\Longrightarrow a\equiv_{M}b$ 

in 2. $Ma$ is the apg detemined from $M$ and $a$ in the proof of theorem 1.9 and $\cong$ is the isomorphism relation between apgs.

## System Extensionality
A System $M$ is Extensional if, for all $a,b\in M$
$$a_M=b_{M}\Longrightarrow a=b$$
aka. if "the children of $a,b$ are equal" implies that $a,b$ are equal

A graph is strongly extensional if for all $a,b\in M$ if 
$$a\equiv_{M} b \Longrightarrow a=b$$
aka. if "a and b are in the maximum bisimulation" implies that $a,b\in M$ 

as such every extensional graph has at most one decoration.

Observe that by [[@aczelNonwellfoundedSets1988#^d4fd80|1.]] every strongly extensional system is extensional. Note that by the extensionality axiom the system $V$ is extensional. By the next result $AFA_2$ expresses a strengthening of the extensionality axiom

> [!Tip] Proposition 2.10
> $$AFA_{2}\Longleftrightarrow \text{$V$ is strongly extensional}$$ 

To show this let us first assume $AFA_2$ and let $a\equiv_{V}b$. Then by exercise 2.5 $a\equiv b$ so that there is an apg $Gn$ and decorations $d_1$ and $d_2$ of $G$ such that $d_{1}n=a$ and $d_{2}n=b$. By $AFA_2$ $d_1=d_2$  so that $a=b$. Thus $V$ is strongly extensional.

Conversely let $V$ be strongly extensional and let $d_1$ and $d_2$ be decorations of a graph $G$. If $x\in G$ then $d_{1}x=d_{2}x$, as $Gx$ is a picture of both $d_{1}x$ and $d_{2}x$. Hence, $d_{1}x\equiv_{V} d_{2}x$, so that $d_{1}x=d_{2}x$, as $V$ is strongly extensional. Thus $d_1=d_2$ so that we have proved $AFA_2$ 

## System Maps
A System Map from the system $M$ to the system $M'$ is a map $\pi :M\rightarrow M'$ such that for $a\in M$ $$(\pi a)_{M'}=\set{\pi b|b\in a_M}$$ If $\pi$ is a bijection then it is a system Isomorphism as every element from one system has a corresponding ellement in the next.

The close relationship which exists between bisimulations and system maps is illustrated by the following results.
> [!Tip] Proposition 2.13
> Let $\pi_{1},\pi_{2}:M\rightarrow M'$ be system maps:
> 1. If $R$ is a bisimulation on $M$ then $$(\pi_{1}\times \pi_{2})R\stackrel{def}{=}\set{(\pi_{1}a_{1},\pi_{2}a_2)|a_{1}Ra_2}$$ is a bisimulation on $M'$
> 2. If $S$ is a bisimulation on $M'$ then $$(\pi_{1}\times \pi_{2})^{-1}S\stackrel{def}{=}\set{(a_{1},a_{2})\in M\times M| (\pi_{1}a_{1})S(\pi_{2}a_{2}))}$$ is a bisimulation on $M$

Let $R$ be a bisimulation on $M$. Let $M_0$ be the system whose nodes are the ordered pairs in the relation $R$ with 
$$(a,b)\rightarrow (a',b')\text{ in $M_0\quad$ if $a\rightarrow a'$ and $b\rightarrow b'$ in $M$}$$
Let $\pi_1,\pi_{2}:M_0\rightarrow M$ be given by $$\begin{align}
\pi_1(a,b)=a\\
\pi_2(a,b)=b
\end{align}$$
for $a,b \in M$ we can show that $\pi_{1,}\pi_{2}$ are system maps. As such this generalises a construction in the proof of [[@aczelNonwellfoundedSets1988#^9ee65d|proposition 2.5]] above to an arbitrary system $M$

2.14 ~
2.15 ~

## Quotients
Let $\pi:M\rightarrow M'$ be a quotient of the class $M$ with respect to the equivalence relation $R$ on $M$ i.e. $\pi$ is a surjective map such that for all $a,b\in M$ $$aRb\Longleftrightarrow\pi a=\pi b$$
Now suppose that $M$ is a system and R is a bisimulation on $M$. Then $\pi$ is a system map, provided that $M'$ be all the pairs $(\pi_a,\pi_b)$ for $(a,b)$ an edge of $M$. We will say that $\pi:M\rightarrow M'$ is a quotient of the system $M$ with respect to the bisimulation equivalence $R$ 

If $\pi:M\rightarrow M'$ is a quotient of the system $M$ with respect to $\equiv_M$ then we say that it is a strongly extensional quotient of $M$

> [!tip] Lemma 2.17
> Every system has a strongly extensional quotient

The essential problem is to define a map $\pi$ with domain the system $M$ such that for $a_{1},a_{2}\in M$ $$a_{1}\equiv_{M}a_{2}\Longleftrightarrow \pi a_{1}=\pi a_2$$ For small $M$ the standard definition of $\pi$ in terms of equibalence classes would work. In general a strong form of global choice would be needed to pick a representative from each equivalence class. Here we shall give an argument that only uses tha local form of $AC$ ...



We can show that $$AFA_{1}\Longleftrightarrow AFA_{1}^{ext}$$
where $AFA_{1}^{ext}$ is :
Every extensional graph has at least one decoration

> [!info] Theorem 2.19
> The following are equivalent for each system $M$:
> 1. $M$ is strongly extensional
> 2. For each (small) system $M_{0}$ there is at most one system map $M_0\rightarrow M$ 
> 3. For each system $M'$ every system map $M\rightarrow M'$ is injective

> [!warning]
> what is $M_0$?


> [!tip] Proposition 2.20
> Let $M$ be a system such that any two nodes of $M$ lie in a common apg of the form $Mc$. Then $M$ is strongly extensional if $Mc$ is strongly extensional for every node $c$ of $M$.

EXPLAIN THIS $\uparrow$
## Pictures

> [!tip] Proposition 2.21
> $$AFA_2\Longleftrightarrow \text{Every canonical picture is strongly extensional}$$

#### Exact Pictures
We will call an apg an exact picture if it has an infective decoration, i.e. distinct nodes are assigned distinct sets by the the decoration. An alternative way to state this is to say that the apg is isomorphic to a canonical picture. Proposition 2.21 can be reformulated as stating that $$AFA_2\Longleftrightarrow\text{ Every exact picture is strongly extensional}$$
> [!tip] Proposition 2.22
> $$AFA_1\Longleftrightarrow\text{Every stongly extensional apg is an exact picture}$$

To show this assume $AFA_1$. Let G be a strongly extensional apg. By $AFA_1$ $G$ has a decoration $d$. So $d:G\rightarrow V$ is a system map. By $(1)\Rightarrow(3)$ of theorem 2.19 $d$ is injective, so that $G$ is an exact picture.

Conversely, let us assume the right hand side of the proposition and show that each graph $G$ has a decoration. Diven the graph $G$ we may form an apg $G'$ by adding a new node $*$ and new edges $(*,a)$ for each node $a$ of $G$. Now let $\pi:G'\rightarrow G''$ be a strongly extensional quotient of $G'$. Then $G''(\pi *)$ is strongly extensional and hence by our assumption it is an exact picture. So $G''$ has an injective decoration $d''$. Now $d$ is a decoration of $G$ where $da=d''(\pi a)$ for each node $a$ of $G$.

Combining the characterisations of $AFA_1$ and $AFA_2$ that we have just obtained we get the main result. 

>[!infor] Theorem 2.23
>AFA is equivalent to: $$\text{An apg is an exact picture if it is strongly extensional}$$

# The Normal Structure Axiom
Here we consider an axiom suggested by a completeness theorem in Kanger for a variant of the predicate calculus. This variant has atomic formulae of the form
$$(s_{1,...,}s_{n})\ \upvarepsilon \ t$$
where $n>0$ and $s_1,...,s_n,t$ are variables or individual constants. The natural semantic for the variant logic is to use structures $\mathcal A=(A,R,...,c^{\mathcal A},...)$ where $A$ is a non-empty set, $R\subseteq A^{+}\times A$ and $c^{\mathcal A}\in A$ for each individual constant $c$. Here $A^{+}=\bigcup_{n>0}A^n$. Let us call such a structure a Kanger structure. The standard completeness theorem will obviously carry over if this semantics is used. Kanger's idea is to modify the semantics by only using 'normal' Kanger structures in the definitions of logical validity and logical consequence. A normal Kanger structure is a structure:
$$\mathcal A=(A,R,...,c^{\mathcal A},...)$$
where 
$$R=\set{(b,a)\in A^{+}\times A|b\in a}$$
At first sight the restriction to normal structures may appear severe in view of the consistency of such sentences as 
$$\exists x((x,x)\ \upvarepsilon\ x)$$
In fact Kranger still succeeds in proving the variant logic complete relative to the normal structures. To do so he obviously has to invoke some principle that will imply the existence of enough non-well-founded sets to guarantee the existence of normal models of sentences such as the above one. 

Kanger formulates a set theoretical principle that is strong enough to imply that every countable Kanger structure is isomorphic to a normal such structure. In view of the Löwenheim-Skolem theorem this consequence implies that the standard completeness theorem will entail the completeness theorem relative to normal structures.

Here we will avoid cardinality considerations and formulate the followoing axiom:

## The Normal Struture Axiom, NSA:
$$\text{Every Kanger structure is isomorphic to a normal one}$$
This axiom is certainly enough to give Kanger's completeness theorem. We have the following result.

> [!info] Theorem 2.24
> $$AFA_{1}\Rightarrow NSA$$

First note that it suffices to probe the result for Kanger structures $(A,R)$ i.e. where there are no individual constants.

In order to apply $AFA_1$ define a graph $G$ as follows:
Let $\overline A$ be the smallest set such that $\set{0}\times A\subseteq \overline A$   and ${1}\times (\bar A\times \bar A)\subseteq \bar A$. Choose $\alpha \in On$ so that there is a bijection $f:A\rightarrow (\alpha-\set{0})$. Of course this requires $AC$. The nodes of $G$a re the elements of the set $\bar A \cup (\set 2 \times \alpha)$. $G$ has edges of the following forms:

............ ?

The axiom $NSA$ is a strengthening of a 'completeness' axiom considered in Gordeev. For any set $c$ let $V|c$ be the graph having the elements of $c$ as nodes and having edges $x\rightarrow y$ when ever $x\in y$ and $x,y\in c$. Call a graph of the form $V|c$ a normal graph. Then gordeev's axiom. $GA$ is:
$$\text{every graph is isomorphic to a normal one}$$
we can show that 
$$NSA\Rightarrow GA$$
# Chapter 3
As in the previous chapters we shall work informally in framework of the axiomatic set theory $ZFC^-$. The aim of this chapter is to form a class model of our set theory, including the new axiom $AFA$.

## Complete Systems
Given a system $M$ an $M$- Decoration of a graph $G$ is a system map $G\rightarrow M$ 
> [!example]
> A $V$-decoration of $G$ is simply a decoration of $G$

$M$ is a complete system if every graph has a unique $M$-decoration. Note that by theorem 2.19 every complete system is strongly extensional. Also note that if $M$ is strongly extensional and every strongly extensional graph has an $M$-decoration then $M$ is complete. Finally, note that $AFA$ holds if and only if the system $V$ is complete.

We turn to the construction of a complete system. Every apg has the form $Ga$ where $G$ is a graph and $a$ is a node of $G$. The class of apgs form a system $V_0$ with edges $(Ga, Gb)$ wherever $G$ is a graph and $a\rightarrow b$ in $G$. Let $\pi_{c}:V_{0}\rightarrow V_c$ be a strongly extensional quotient of $V_0$ 

> [!tip] Proposition 3.2
> For each system $M$ there is a unique system map $M\rightarrow V_c$ 

If $a\in M$ then $Ma \in V_0$. Moreover the map $M\rightarrow V_0$ that assigns $Ma$ to $a\in M$ is clearly a system map. Composing with the system map $\pi_c :V_0\rightarrow V_c$ we obtain a system map $M\rightarrow V_c$. The uniqueness of this system map follows by theorem 2.19 from the strong extensionality of $V_c$.

as a Corollary we can say $V_c$ is complette

> [!info] Theorem 3.4 
> The following are equivalent for a system $M$
> 1. For each system $M'$ there is a unique system map $M' \rightarrow M$ 
> 2. $M$ is complete
> 3. $M\cong V_c$ 

That $3$ implies $1$ is an immediate consequence of proposition 3.2. That 1 implies 2 is trivial. We now show that 2 implies 3. Let $M$ be a complete system. Let $\pi:M\rightarrow V_c$ be the unique system map which exists by proposition 3.2. The map $\pi$ is injective as $M$ is strongly extensional. If $a\in V_c$ then $V_{c}a$ is an apg with a unique $M$-decoration. ....

## Full systems
A system $M$ is a Full system if for every set $x\subseteq M$ there is a unique $a\in M$ such that $x=a_M$ 
>[!example]
>1. $V$ is a full system. More generally whenever $M$ is a class such taht $M= powM$ then $M$ is a full system when $a\rightarrow b$ in $M$ if $b\in a\in M$. For example the class $V_{wf}$ is the smallest class $M$ such that $M=powM$. Note that $V$ is the largest such class $M$ and the foundation axiom can be expressed by the equation $$V=V_{wf}$$ 
>2. if $\pi:M\rightarrow M$ is any bijection on a full system $M$ then we can obtain a new full system $M_\pi$ having the same nodes as $M$ but where $$a\rightarrow b \in M_\pi\Leftrightarrow\pi a \rightarrow b \in M $$ 
>

The following are equivalent for a full system $M$:
- For each full system $M'$ there is a unique system map $M\rightarrow M'$
- $M$ is well founded
- $M\cong V_{wf}$ 

> [!tip] Proposition 3.7
> Each complete system is full

We can show this in two ways: I wont do that now though. That is a problem for future sander.

## The Interpretation of AFA
Any system $M$ determines an interpretation of the language of set theory in whihc the varaibles range ove the nodes of $M$ and the predicate symbol $\in$ is interpreted by the relation $\in_M$, where for $a,b\in M$$$a\in_{M}b\Longleftrightarrow a \in b_M$$ When the system $M$ is full this interpretation models all the axioms of $ZFC^-$. 
>[!info] Theorem:
>Each complete system is a model of $ZFC^- +AFA$ 
>

Let $M$ be a complete system. Then $M$ is full and hence a model of $ZFC^-$, by Rieger's theorem. So it remains to prove that $M$ is a model of $AFA$. If $x$ is a subset of 
---
tags:
- math/abstract-algebra
---
Within a [[Set]] it is sometimes natural to talk about different elements being related in some way. For example in $\mathbb Z$ we could say that $x,y\in\mathbb Z$ are related if $x-y$ is divisible by 2. Said another way, $x$ and $y$ are related is they are both odd or both even . This idea can be formalised as something called an equivalence relation.
>[!abstract] Definition
>An equivalence relation on a set $S$ is a subset $U\subset S\times S$ satisfying:
>1. $(x,y)\in U\Leftrightarrow (y,x)\in U$ (symmetric property)
>2. $\forall x\in S,(x,x)\in U$ (reflexive property)
>3. Given $x,y,z\in S, (x,y)\in U$ and $(y,z)\in U\Rightarrow (x,z)  \in U$ (transitive property)

If $U\subset S\times S$ is an equivalence relation then we say that $x,y\in S$ are equivalent if and only if $(x,y)\in U$. In more convenient notation, we write $x\sim y$ to mean that $x$ and $y$ are equivalent.

## Equivalence Classes
>[!abstract] Definition
>Let $\sim$ be an equivalence relation on the set $S$. Let $x\in S$.  The equivalence class containing $x$ is the subset 
>$$[x]:=\set{y\in S|y\sim x}\subset S$$

### Remarks
1. Notice that the reflexive property implies that $x\in[x]$. Hence equivalence classes are non-empty and the union is $S$ 
2. The symmetric and transitive properties imply that $y\in [x]$ if and only if $[y]=[x]$. Hence two equivalence classes are equal or disjoint. It should also be noted that we can represent a given equivalence class using any of its members using the $[x]$ notation

Any [[Partitions|partition]] of a set naturally gives rise to an equivalence relation whose equivalence classes are the members of the partition. The conclusion of all this is that an equivalence relation on a set i the same as a partition. In the example given above, the equivalence classes are the odd integers and the even integers.

\cong$\cong$ 
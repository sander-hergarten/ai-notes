---
tags:
- math/graphs
---
An infinite graph $G$ consists of an infinite set $V(G)$ of elements called vertices and an infinite family $E(G)$ of unordered pairs of elements of $V(G)$ called edges. if $V(G)$ and $E(G)$ are both countably infinite but $E(G)$ finite, then $G$ is a countable graph.
We exclude the possibility of $V(G)$  being infinite but $E(G)$ finite, as such objects are merely finite graphs together with infinitely many isolated vertices or of $E(G)$ being infinite and V(G) finite, as such objects are essentially finite graphs but with infinitely many loops or multiple edges.

Many of the default graph definitions([[Graphs#Operations and Terminology|adjacent, incident, isomorphic, etc.]]) extend immediately to infinite graphs. The degree of a vertex $v$ of an infinite graph is the cardinality of the set of edges incident to $v$, and may be finite or infinite. 

An infinite graph, each of whose vertices has finite degree, is locally finite, such as the infinite square lattice and the infinite triangular lattice
![[Pasted image 20230618123437.png]]

A locally countable infinite graph is one where each vertex has countable degree. 

> [!quote]  Theorem
 > every connected locally countable infinite graph is a countable graph
 > 
 >every connected locally finite infinite graph is a countable graph
 

## Walks
There are essentially three types of walks in a infinite graph $G$:
1. a finite walk is defined exactly as the [[Trails, Paths and Cycles#Walk|traditional walk]] is
2. one-way infinite walk with initial vertex $v_0$ is an infinite sequence of edges of the form $$v_0v_1, v_1v_2,...$$
3. two-way infinite walks are an infinite sequence of edges of the form:$$...,\ v_{-2}v_{-1},\ v_{-1}v_0,\ v_0v_1,\ v_1v_2,\ ...$$
One way and two way infinite trails and paths are defined analogously, as are the length of a path and the distance between vertices. The following result, known as König's lemma, tells us that infinite paths are not difficult to come by.
> [!quote] Theorem 
> Let $G$ be a connected locally finite infinite graph. Then for any vertex $v$ of $G$, there exists a one-way infinite path with initial vertex $v$

we can derive:
> [!quote] Theorem 
> If $G$ is a countable graph, every finite subgraph of which is planar, then $G$ is planar

## Infinite Eulerian Paths
A connected infinite graph $G$ is Eulerian if there exists a two way trailthat includes every edge of $G$, called a two way eulerian trail. 
>[!quote] Theorem
>Let $G$ be a connected countable graph which is Eulerian. Then:
>1. $G$ has no vertices of odd degree
>2. for each finite dubgraph $H$ of $G$, the infinite graph $H$ obained by deleting form $G$  the edges of $H$ has at most two infinite connected components.
>3. if in addition, each vertex of $H$ has even degree, then $H$ has exactly one infinite connected component. 

The conditions given in the previous theorem are not only necessary but also sufficient. And as such if the conditions are met the graph is Eulerian




---
tags:
- math/graph-theory
- ruff-note
aliases:
- graphs
- graph
- Graph
---
# Graph Types
## Simple Graph
A simple graph $G$ consists of. a non-empty finite set $V(G)$ of elements called vertices (or nodes), and a finite set $E(G)$ of distinct unordered pairs of distinct elements of $V(G)$
called edges. We call $V(G)$ the vertex set and $E(G)$ the edge set of $G$. An edge $\{v, w\}$ is said to join the vertices $v$ and $w$ and is usually abbreviated to $vw$.

## General Graph 
When removing the distinct constraints on the edge set we have a General graph ($E(G)$ is a finite family of unordered pairs of elements of $V(G)$). This allows for loops and the change of a set to a family enables multiple edges between the same pair. 

## Null Graph 
A graph whose edge-set is empty is a null graph. we denote the null graph on $n$ vertices by $N_n$

## Complete graphs
A simple graph in which each pair of distincy vertices are adjacent is a complete graph. We denote the complete graph on $n$ vertecies by $K_n$. These graphs have $\frac{n(n-1)}{2}$ edges
![[Pasted image 20230615164529.png]]
($K_4$)

## Regular graphs 
A graph in which each vertex has the same degree is a regular graph. If each vertex has degree $r$, the graph is regular of degree $r$ or $r$-regular. Of special importance are the cubic graphs, which are regular of degree 3; an example of a cubic graph is the petersen graph. Note that the null graph $N_n$ is regular of degree $0$, the cycle graph $C_n$ is regular of degree 2, and the complete graph $K_n$ is regular degree $n-1$.
![[Pasted image 20230615170907.png]]
(Petersen graph)

## Cycle Graphs, Path Graphs and Wheels
A connected graph that is regular of degree 2 is a cycle graph. We debote the cycle graph on $n$ vertices by $C_n$. The graph obtained from $C_n$ by removing an edge is the path graph denoted by $P_n$. The graph, obtained from $C_{n-1}$ by joining each vertex to a new vertex $v$, is the wheel on $n$ vertices, denoted by $W_n$. 
![[Pasted image 20230615165114.png]]
($C_6$, $P_6$, $W_6$) 

## Platonic Graphs
of interest among the regular graphs are the Platonic graphs, formed from the vertices and edges of the five regular (Platonic) solids.
![[Pasted image 20230615171120.png]]

## Bipartite graphs
If the vertex set of a graph $G$ can be split into two disjoint sets $A$ and $B$ so that each edge of $G$ joins a vertex of $A$ and a vertex of $B$, then $G$ is a bipartite graph. Alternatively, a bipartite graph is one whose vertices can be coloured black and white in such a way that each edge joins a black vertex in A and a white vertex in B. 
![[Pasted image 20230615171634.png]]

A complete bipatite graph is a bipartite graph in which each vertex in $A$ is joined to each vertex in $B$ by just one edge. We denote the bipartite graph with $r$ black vertices and $s$ white vertices by $K_{r,s}$ The [[Graphs#Complete graphs|completeness rules]] still apply.
![[Pasted image 20230615172223.png]]
## Cubes
Of special interest among the regular bipartite graphs are the cubes. The $k$-cube $Q_k$ is the graph whose vertices correspond to the sequences $(a_1,a_2,...,a_k)$, where each $a_i\in \{0, 1\}$, and whose edges join those sequences that differ in just one place. The graph of the cube is the graph $Q_3$. In the $k$-cube following conditions are true:
$$|V(Q_k)|= 2^k \quad |E(Q_k)|=k2^{k-1}$$
## The complement of a simple graph
If $G$ is a simple graph with vertex set $V(G)$, ist complement $\bar{G}$ is the simple graph with vertex set $V(G)$ in which two vertices are adjacent if and only if they are not adjacent in $G$.

# Operations and Terminology
## Connectedness
We can combine two [[Graphs]]. if the two graphs are $G_1 =(V(G_1), E(G_1))$ and $G_2=(V(G_2), E(G_2))$, where $V(G_1)\cup V(G_2)= \emptyset$,  then their union $G_1 \cup G_2 = (V(G_1)\cup V(G_2), E(G_1)\cup E(G_2))$ 

A Graph is Connected if it cannot be expressed as the union of two graphs, and disconnected otherwise. Any disconnected Graph can be expressed as the union of connected graphs, each of which is a component of G.
## Degrees
A degree of a vertex is the amount of edges adjacent to the vertex
## Isomorphism
Two [[Graphs]], $G_1$ and $G_2$, are isomorphic if there is a one-one correspondence between the verticies of $G_1$ and those of $G_2$ such that the number of edges joining any two vertices of $G_1$ is equal to the number of edges joining the corresponding vertices of $G_2$.

The following graphs are isomorphic under the correspondence:
$$u\leftrightarrow l,\ v\leftrightarrow m,\ w\leftrightarrow n,\ x\leftrightarrow p,\ y\leftrightarrow q, z\leftrightarrow r$$
![[Pasted image 20230615160144.png]]

## Homeomorphism
Two graphs are homeomorphic if both can be obtained from the same graph by inserting new vertices of degree 2 into its edges. For example any two cycle graphs are homeomorphic, as are the following
![[Pasted image 20230615223131.png]]

## Contractibility
A graph $H$ is contractible to a graph $G$ if we can obtain $G$ by successively contracting edges of $H$. For example, The Petersen graph is contractible to $K_5$, as we can see by contracting the five 'spokes' joining the inner and outer 5 cycles. 
![[Pasted image 20230615224657.png]]

## Adjacency
We say that two vertices $v,w\in V(G)$ are adjacent if there is an edge joining them, and the the vertices are then incident with such an edge. Similarly two distinct edges  are adjacent if they have a vertex in common.
![[Pasted image 20230615163549.png]]
A vertex with degree 0 is an isolated vertex and with degree 1 is an end vertex.
## Collapsibility
A graph $G$ is $k$-collapsible if $\delta(G)=k$  and any proper induced subgraph has smaller minimum degree. Collapsible graphs can be viewed as lower extremal graphs for monocore graphs

## Thickness
A graphs thickness is defined to be the smallest number of planar graphs that can be superimposed to form $G$. Like the crossing number, the thickness is a measure of how unplanar a graph is. For example the thickness of a planar graph is $1$, and of $K_5$ and $K_{3,3}$ is 2. A lower bound for thickness of a graph is easily obtained from Eulers formula. Surprisingly, this trivial lower bound frequently turns out to be the correct value.

> [!quote] Thickness
> Let $G$ be a simple graph with $n\ge 3$ vertices and $m$ edges. then the thickness $t(G)$ of $G$ satisfies the inequalities $$t(G)\ge \left\lceil \frac{m}{3n-6}\right\rceil \quad and\quad t(G)\ge \left\lfloor\frac{m+3n-7}{3n-6}\right\rfloor$$


## Subgraphs
A subgraph of a graph G is a graph, each of whose vertices belongs to $V(G)$ and each of whose edges belongs to $E(G)$. 

We also denote by $G\textbackslash e$ the graph obtained by taking an edge e and contracting it (removing it and identifying its ends so that the resulting vertecies are incident with  those edges, other than $e$, that were originally incident with the vertecies.
![[Pasted image 20230615162807.png]]

## Matrix Representation
If $G$ is a graph with vertices labelled $\{1, 2,...,n\}$, its adjacency matrix $A^{n\times n}$ whose $ij$-th entry  is the number of edges joining vertex $i$ and vertex $j$. 

If in addititon the edges are labelled $\{1,2,...,m\}$, its incidence matrix $M^{n\times m}$ whose $ij$-th entry is 1 if vertex $i$ is incident to edge $j$ and $0$ otherwise. for example:
![[Pasted image 20230615164041.png]]

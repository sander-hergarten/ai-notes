A directed graph, or digraph, $D$ consists of a non-empty finite set $V(D)$ of elements called vertices, and a finite family $A(D)$ of ordered pairs of elements of $V(D)$ called arcs. We call $V(D)$ the vertex set and $A(D)$ the arc family of D. An arc ($v,w$) is usually abbreviated to $vw$. In a graph drawing the ordering of the vertices in an arc are being indicated by an arrow.
![[Pasted image 20230618160006.png]]
If $D$ is a digraph the graph obtained from $D$ by removing the ordinality is the underlying graph of D

D is a simple digraph if the arcs of $D$ are all distinct and if there are no loops. Note that the underlying graph of a simple digraph need not be a simple graph

we can imitate many of the definitions given for [[Graphs#Operations and Terminology|graphs]]. 

For example two graphs are isomorphic if there is an isomorphism between their underlying graphs that preserve the ordering of the vertices in each arc. 

## Adjancency
Two vertices are adjacent if there is an arc in $A(D)$ of the form $vw$ or $wv$. The vertices $v$ and $w$ are incident to such an arc. If $D$ has vertex set $\{v_1, ..., v_n\}$, the adjacency matrix of $D$ is the $n\times n$ matrix $\textbf{A} =(a_{ij})$ where $a_{ij}$ is  the number of arcs from $v_i$ to $v_j$. 

## Parent and Child
If there is an arc going if the form $vw$ then $v$ is the parent of $w$ and $w$ is a child of $v$. The set of all parents of $v$ is denoted by $\pi_v$ or $\pi(v)$. 

## Walks
A walk in a digraph $D$ is a finite sequence of arcs of the form $v_0v_1,v_1v_2,...,v_{m-1}v_m$. In an analogous way we can define trails, directed paths and directed cycles. Note that although a trail cannot contain a given arc $vw$ more than once, can contain both $vw$ and $wv$. A directed graph is acyclic if it has no cycles. In this case we say that the graph is a directed acyclic graph or DAG.
### Undirected paths
ignoring the direction of the arcs we can create an undirected path.

## Ancestors and Descendants
Vertex $v$ is an ancestor of $w$ if there is a directed path from $v$ to $w$. We also say that $w$ is a descendant of $v$

## Colliders
A configuration of the form 
$$x\rightarrow y\leftarrow z$$
is called a collider. A configuration no of that for is called a non-collider

## Connectedness
The two most useful types of connected digraph correspond to wether or not we take account of the direction of the arcs. 

A Digraph is connected the underlying graph of $D$ is a connected graph. $D$ is strongly connected if, for any two vertices $v$ and $w$ of $D$, there is a path from $v$ to $w$. 

Every strongly connected digraph is connected, but not all connected digraphs are strongly connected. 

## Orientability
we define a graph $G$ to be orientable if each edge of $G$ can be directed sp that the resulting digraph is strongly connected. 

Note that any Eulerian graph is orientable since the Eulerian trail can be followed directing the edges in the direction of the trails as we go.

>[!quote] Theorem
>Let $G$ be a connected graph. Then $G$ is orientable if and only if each edge of $G$ is contained in at least one cycle

## Critical path
We construct a weighted digraph and find the longest path. this is the critical path.

## Eulerian digraphs and tournaments
A connected digraph $D$ is Eulerian if there exists a closed trail containing every arc of $D$. Such a trail is an Eulerian trail. 

The out-degree of a vertex $v$ of $D$ is the number of arcs of the form $vw$ and is denoted by $\text{outdeg}(v)$, similarly the in-degree is the same thing just for ingoing arcs and is denoted $\text{indeg}(v)$

We call $\sum^{|V(D)|}_{n=0} \text{indeg}(v_n)-\text{outdeg}(v_n) = 0$ the handshaking dilemma.

For later convenience we define a source of $D$ to be a vertex with in-degree 0, and a sink of $D$ to be a vertex with out-degree 0. Any Eulerian digraph with at least one arec ahs no sources or sinks.

> [!quote] Theorem
> A connected digraph is Eulerian if and only if for each vertex $v$ of $D$ $\text{outdeg}(v)=\text{indeg}(v)$

### Hamiltonian Digraph
A digraph $D$ is Hamiltonian if there is a cycle that includes every vertex of $D$. A non-Hamiltonian digraph that contains a path passing through every vertex is semi-Hamiltonian. 

### Dirac's Theorem
Let $D$ be a strongly connected digraph with $n$ vertices. If $\text{outdeg}(v)\geqq\frac{n}{2}$ and $\text{indeg}(v)\leqq\frac{n}{2}$ for each vertex $v$, then $D$ is Hamiltonian

A tournament is a digraph in which any two vertices are joined by exactly one arc. Such a digraph can be used to record the result of a tennis tournament, or any other game in which draws are not allowed.Because tournaments may have sources or sinks they are not in general Hamiltonian. However, the following theorem shows that every tournament is nearly Hamiltonian
> [!quote] Theorem
> 1. Every non-Hamiltonian tournament is semi-Hamiltonian
> 2. every strongly connected tournament is Hamiltonian


## Probability
Let $\mathcal G$ be a DAG with vertices $V=(X-1,...,X_k)$

If $\mathbb P$ is a [[Distributions|distribution]] for $V$ with probability function $p$, we say that if $\mathbb P$ is Markov to $\mathcal G$ or that $\mathcal G$ represents $\mathbb P$ if 
$$p(v)=\prod^k_{i=1}p(x_i|\pi_i)$$
where $\pi_i$ are the parents of $X_i$. The set of distributions represented by $\mathcal G$ is denoted by $M(\mathcal G)$



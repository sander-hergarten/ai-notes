
## Walk
Given a [[Graphs|graph]] $G$, a walk in $G$ is a finite sequence of edges of the form $v_0v_1,v_1v_2,...,v_{m-1}v_m$ also denoted by $v_0\rightarrow v_1\rightarrow v_2\rightarrow ...\rightarrow v_m$  in which any two consecutive edges are adjacent or identical. such a walk determines a sequence of vertices. we call $v_0$ the initial vertex and $v_m$ the final vertex of the walk. The number of edges in a walk is called its length.

## Trail, Path
A walk in which all the edges are distinct is a trail. If, in addition, the vertices are distinct (except, possibly $v_0=v_m$) then the trail is a path. 

## Closed Trails, Paths and Cycles
Paths and trails are closed if $v_0=v_m$ and a closed path containing at least one edge is a cycle. A cycle of length 3 is a triangle



A few derivable Theorems are:
- A graph is connected if and only if there is a path between each pair of vertices. 
- A graph is [[Graphs#Bipartite graphs|bipartite]] if and only if each cycle has even length.
- Let $G$ be a simple graph on  $n$ verticies. If $G$ has $k$ components, then the number $m$ of edges of $G$ satisfies:$$n-k\le m\le \frac{(n-k)(n-k+1)}{2}$$
- Any simple graph with $n$ vertices and more than $\frac{(n-1)(n-2)}{2}$ edges is connected
- If $G$ is a graph in which the degree of each vertex is at least 2, then $G$ contains a cycle.

#### Disconnecting Set
A disconnecting set of $G$ is a set of edges whose removal increases the number of components of $G$

#### Cutset
A cutset of $G$ is a disconnecting set, no proper subset of which is a disconnecting set.

#### Bridge
If a cutset has only one edge $e$, we call $e$ a bridge

#### Edge Connectivity 
If $G$ is connected, its edge connectivity $\lambda(G)$ is the size of the smallest cutset in $G$. We also say that a graph $G$ is $k$-edge connected if $\lambda(G)\ge k$ 

#### Separating Set
Defined analogously to the edge definitions. A separating set is a set of vertices which disconnect a connected graph $G$ when removed.

#### Cut-Vertex
if a separating set contains only one vertex we call that vertex a cut-vertex

#### Vertex Connectivity (Connectivity)
If $G$ is connected and not a [[Graphs#Complete graphs|complete graph]], its connectivity $\kappa(G)$ is the size of the smallest separating set in $G$. We also say that a graph $G$ is $k$-connected if $\kappa(G)\ge k$.











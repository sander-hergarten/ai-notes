---
tags:
- math/graph-theory
---
Planarity is a notion in topological graph theory and describes when a graph can be drawn in the plan and on other surfaces.

## Planar Graphs
A planar graph is a graph that can be drawn in the plane without crossings; that is, so that no two edges intersect geometrically except at a vertex to which both are incident. Any such drawing is a plane drawing. For abbreviation we often use plane graph for a plane drawing of a planar graph. For example below there three drawings of the planar graph $K_4$ but only the second and third are plane graphs
![[Pasted image 20230615220221.png]]
It was proved independently that every simple planar graph can be drawn with straight lines.

### Kuratowski's Theorem
Not all graphs are planar such as $K_{3,3}$ and $K_5$ which are called non-planar. Note that every subgraph of a planar graph is planar and that every graph with a non-planar subgraph must be non-planar. In fact $K_{3,3}$ and $K_5$ are the building blocks of non-planar graphs, in the sense that every non-planar graph must 'contain' at least one of them. 
> [!quote] Theorem
> A graph is planar if and only if it contains no subgraph [[Graphs#Homeomorphism|homeomorphic]] to $K_5$ or $K_{3,3}$

From Kuratowski's theorem we can obtain another criterion for planarity 
> [!quote] Theorem
> A graph is planar if and only if it contains no subgraphs contractivle to $K_5$ or $K_{3,3}$ 

### Crossing Number
If we try to draw $K_5$ or $K_{3,3}$  on the plane, then there must be at least one crossing of edges, since these graphs are not planar. However, we do not need more than one crossing, and we say that $K_5$ or $K_{3,3}$ have crossing number 1.

More generally, the crossing number $cr(G)$ of a graph $G$ is the minimum number of crossings that can occur when $G$ is drawn in the plane. Thus the crossing number can be used to measure how 'unplanar' $G$ is. For example, the crossing number of any planar graph is 0, and $cr(K_5)=cr(K_{3,3})=1$. The word 'crossing' always refers to the intersection of just two edges. Crossings of more edges are not permitted and will lead to instant death of the author.

## Euler's Formula
### Faces
If $G$ is a planar graph, then any plane drawing of $G$ divides the set of points of the plane not lying on $G$ into regions, called faces for example, the plane graphs below have eight faces and four faces respectively. Note that, in each case, the face $f_4$ is unbounded and is thus called the infinite face.
![[Pasted image 20230615230832.png]]

The infinite face can be chosen from any face of the graph. This can be made obvious by mapping the graph onto the surface of a sphere by stereographic projection. The sphere can then be rotated until the point of projection point (the north pole) lies inside the face we want as the infinite face, and then project the graph down onto the plane tangent to the sphere at the south pole. The chosen face is now the infinite face
![[Pasted image 20230615231339.png]]

We now state Euler's Formula that tells us that whatever plane drawing of a planar graph we take, the number of faces is always the same and is given by a simple formula. 
> [!quote] Euler's Formula
> Let $G$ be a plane drawing of a connected planar graph and let $n$,$m$ and $f$ denote respectively the number of vertices, edges and faces of $G$. Then $$n-m+f=2$$
> extended for disconnected graphs let $n$, $m$, $k$ and $f$ denote respectively the number of vertices, edges, components and faces $$n-m+f=k+1$$
### Polyhedral Graph
Project the polyhedron out onto its circumsphere and then use stereographic projection to project it down onto the plane. The resulting graph is a 3-connected plane graph in which each face is bounded by a polygon. This is a polyhedral graph

All the results mentioned so far in this section apply to arbitrary plane graphs. We now restrict ourselves to simple graphs:
> [!quote] Theorem
> 1. If $G$ is a connected simple planar graph with $n\ge 3$ vertices and m edges, then $m\le 3n-6$ 
> 2. If, in addition, $G$ has no triangles, then $m\le 2n-4$

> [!quote] Theorem
> Every simple planar graph contains a vertex of degree at most $5$






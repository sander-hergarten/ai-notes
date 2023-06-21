## Colouring vertices
We shall assume that all graphs are [[Graphs#Simple Graph|simple]] and connected.

If $G$ is a graph without loops, then $G$ is $k$-colourable if we can assign one of $k$ colours to each vertex so that adjacent vertices have different colours.

If $G$ is $k$-colourable, but not ($k$-1)colourable, we say that  $G$ is $k$-chromatic, or that the chromatice number of $G$ is $k$ and write $\chi(G)=k$ .
![[Pasted image 20230618131034.png]]
($\chi(G)=4$)
- It is clear that $\chi(K_N)=n$, and so there are graphs with arbitrarily high chromatic number. At the other end of the scale.
- $\chi(G) = 1$ if  and only if $G$ is a null graph
- $\chi(G) =2$ if and only if $G$ is a non-null bipartite graph.
Note that every tree is 2-colourable, as is any cycle graph with an even number of vertices.

It is not know which graphs are 3-chromatic, although it is easy to give examples of such graphs. These examples include the cycle graphs or wheels with an odd number of vertices and the Petersen graph. 

If the graph has $n$ vertices, then its chromatic number cannot exceed $n$,and if the graph contains $K$, as a subgraph. then its chromatic number cannot be less than $r$, but these results do not take us very far in general. If, however, we know the degree of each vertex then we can make preditions 
>[!quote] Theorem
>If $G$ is a  simple graph with largets vertex-degree $\Delta$ then $G$ is ($\Delta +1$)-colourable 

We can strengthen this theorem a little to give the following resul, know as Brook's theorem. 
>[!quote] Theorem 
>If $G$ is a simple connected graph which is not a complete graph, and if the largest vertex-degree of $G$ is $\Delta\ge 3$ then $G$ is $\Delta$-colourable

If we restrict our attention to planar graphs we can prove that every simple planar graph is 4-colourable. 
>[!quote] Theorem
>a simple planar graph is 4-colourable


## Colouring maps
Given a map containing several countries, we may ask how many colours are needed to colour them so that no two countries with a boundary line in common share the same colour. 

In order to make this statement precise, we must explain what we mean by a 'map'.  we define a map to be a 3-connected plane graph. Thus a map contains no cutsets with 1 or 2 edges, and in particular no vertices of degree 1 or 2. 

We define a map to be $k$-colourable(f) if its faces can be coloured with $k$ colours so that no two faces with a boundary edge inc ommon have the same colour. TO avoid confusion, we use  $k$-colourable($v$) to mean  $k$-colourable in the usual sense. 

as such the four-colour theorem for maps is the assertion that every map is 4-colourable($f$). 

If and only if map $G$ is a Eulerian graph it is 2-colourable($f$) 

Let $G$ be a plane graph without loops, and let $G^*$ be a geometric dual of $G$. Then $G$ is k-colourable(v) if and only if $G^*$ is $k$-colourable(f)

as such since every map is a simple planar graph the 4-colourable property of the dual of $G$ applies

Duality can also be used to prove the following theorem.
> [!quote] Theorem
> Let $G$ be a cubic map. Then $G$ is 3-colourable(f) if and only if each face is bounded by an even number of edges.

In the above theorem, we assumed that the map is cubic. This need not be a severe restriction, as the following theorem shows.
> [!quote] Theorem
> In order to prove the four-colour theorem, it is sufficient to prove that each cubic map is 4-colourable($f$)

## Colouring Edges
A graph $G$ is $k$-colourable(e) or $k$-edge colourable if its edges can be coloured with $k$-colours so that no two adjacent edges have the same colour.

If $G$ is $k$-colourable(e) but not ($k-1$)-colourable(e), we say that the chromatic index of $G$ is $k$, and write $\chi' (G) =k$ 
![[Pasted image 20230618152505.png]]
($\chi'(G)=4$) 

If $\Delta$ is the largest vertex degree of $G$ then $\chi'(G)\ge\Delta$. The following result, known as Vizing's theorem, gives very sharp bounds for  the chromatic index of a simple graph $G$. 
>[!quote] Theorem
>IF $G$ is a simple graph with largest vertex-degree $\Delta$, then $\Delta\le\chi'(G)\le\Delta+1$ 

It is not known which graphs have chromatic index $\Delta$ and which have chromatic index $\Delta+1$. However the results for particular types of graphs can easily be found. 
$$\chi'(K_n)=\begin{cases}n-1&\quad \text{if }n\text{ is even}\\ n &\quad \text{if }n\text{ is odd}\end{cases}$$

>[!quote] Theorem
>The four-colour theorem is equivalent to the statement that $\chi'(G)=3$ for each cubic map $G$

Dénes König on the chromatic index of a bipartite graph
> [!quote] Theorem
> If $G$ is a bipartite graph with largest vertex-degree $\Delta$, then $\chi'(G)=\Delta$

$$\chi'(K_{r,s}=\max(r,s)$$
## Chromatic polynomials
Let $G$ be a simple graph, and let $P_G(k)$ be the number of ways of colouring the vertices of $G$ with $k$ colours so that no two adjacent vertices have the same colour. $P_G$ is called the chromatic function of $G$. 

>[!warning]
>INCOMPLETE: I dont understand these and dont want to check them in the moment



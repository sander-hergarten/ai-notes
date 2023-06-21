A [[Graphs#Connectedness|connected graph]] $G$ is Eulerian if there exists a [[Trails, Paths and Cycles#Closed Trails, Paths And cycles|closed trail]] containing every edge of $G$. Such a trail is an Eulerian trail. Note that this definition requires each edge to be traversed once and only once.

## Semi Eulerian Graphs
A non-Eulerian graph $G$ is semi-Eulerian if there exists a trail containing every edge of $G$.

>[!Note] 
> 1. A connected graph $G$ is Eulerian if and only if the degree of each vertex of $G$ is even
> 2. A connected graph is Eulerian if and only if its set of edges can be split up into disjoint cycles
> 3. A connected Graph is semi-Eulerian if and oly if it has exactly two vertices of odd degree
> 
> In a semi-Eulerian graph, any semi-Eulerian trail must have one vertex of odd degree as its initial vertex and the other as its final vertex. Also, by the handshaking lemma, a graph cannot have exactly one vertex of odd degree.

## Fleury's algorithm
Let $G$ be and Eulerian graph. Then the following construction is always possible, and produces an Eulerian trail of $G$:
> [!quote] Eulerian trail construction
> Start at any vertex $u$ and traverse the edges in an arbitrary manner, subject only to the following rules:
> 1. erase the edges as they are traversed, and if any isolated vertices result erase them too
> 2. at each stage, use a [[Trails, Paths and Cycles#Bridge|bridge]] only if there is no alternative


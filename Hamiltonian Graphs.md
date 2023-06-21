A similar problem to the one solved by the [[Eulerian Graphs]] is to determine whether there exists a closed trail passing exactly once through each vertex of $G$. Such a trail must be a [[Trails, Paths and Cycles#Closed Trails, Paths and Cycles|cycle]], except when $G$ is the Null graph with one vertex. Such a cycle is a Hamiltonian Cycle and $G$ is a Hamiltonian graph. A non-Hamiltonian graph $G$ is semi-Hamiltonian if there exists a path passing through every vertex.

## Dirac's Theorem
We have sufficient conditions to decide if a connected graph is Eulerian. Unfortunately not much is known about Hamiltonian graphs and as such most existing theorems don't fully describe Hamiltonian graphs. The most celebrated assumption is Dirac's theorem.
> [!quote] Theorem
> If $G$ is a simple graph with $n \ge 3$ vertices, and if $deg(v)>n/2$ for each vertex $v$, then $G$ is Hamiltonian

This is derived from a a more general result of O. Ore:
> [!quote] O. Ore 1960
> If $G$ is a simple graph with $n\ge 3$ vertices, and if $$deg(v)+deg(w)\ge n$$ for each pair of non-adjacent verticies $v$ and $w$, then $G$ is Hamilitonian





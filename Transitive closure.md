---
tags:
- 
aliases:
- 
---
In mathematics the transitive closure $R^+$ of a homogeneous Binary relation $R$ on a set $X$ is the smallest relation on $X$ that contains $R$ and is transitive. For finite sets, "smallest" can be taken in its usual sense, of having the fewest related pairs; for infinite sets $R^+$ is the unique minimal transitive superset of $R$ 

> [!info] Example
> If $X$ is a set of ariports and $xRy$ means "there is a direct flight from airport $x$ to airport $y$" (for $x$ and $y$ in $X$), then the transitive closure of $R$ on $X$ is the relation $R^+$ such that $xR^{+}y$ means "it is possible to fly from $x$ to $y$ in one or more flights"

More formally, the transitive closure of a binary relation $R$ on a set $X$ is the smallest [[Equivalence Relation|transitive relation]] $R^+$ on $X$ such that $R\subseteq R^+$. If $R^+=R$ then $R$ is transitive is transitive 

## Transitive reduction
transitive reduction adduces a minimal relation $S$ from a given relation $R$ such that they have the same closure, that is, $S^+=R^+$, however many different $S$ with this property may exist. 

----
## References
https://en.wikipedia.org/wiki/Transitive_closure
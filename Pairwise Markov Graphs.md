let $V$ be a set of random variable with distribution $\mathbb P$. Construct a [[Graphs| graph]] with one vertex for each random variable in $V$. Suppose we omit the edge between a pair of variables if they are independent given the rest of the variables:
$$\text{no edge between $X$ and $Y$}\Leftrightarrow X\perp \!\!\! \perp Y|\text{rest}$$
where "rest" refers to all the other variables besides $X$ and $Y$. This type of graph is called a pairwise Markov graph. 

![[Pasted image 20230625195626.png]]
($X \perp \!\!\! \perp Z|{Y,W}$ and $Y\perp \!\!\! \perp W|{X,Z}$)

The graph encodes a set of pairwise [[Conditional Independence|conditional independence]] relations. these relations imply other conditional independence relations

Fortunately we can read these other conditional independence relations directly from the graph as well.

# Global and Pairwise Markov Property
Let $\mathcal G=(V,E)$ be a pairwise Markov graph for a distribution $\mathbb P$. Let $A,B, C$ be distinct subsets of $V$ such that $C$ separates $A$ and $B$. Then $A\perp \!\!\! \perp B|C$  ^e9c4c6

If $A$ and $B$ are not connected (i.e. there is no [[Trails, Paths and Cycles|path]] from $A$ to $B$) then we may regard $A$ and $B$ as being separated by the empty set. This implies that $A\perp \!\!\! \perp B$ 

The independence condition, in [[Graphical Models#^e9c4c6|this theorem]], is called the global Markov property. We thus see that the pairwise and global Markov properties are equivalent. Let us state this precisely.

Given a graph $\mathcal G$ let $M_{\text{pair}}(\mathcal G)$ be the set of distributions which satisfy the pairwise Markov property: Thus $\mathbb P\in M_{\text{pair}}(\mathcal G)$ if, under $\mathbb P$, $X\perp \!\!\! \perp Y|\text{rest}$ if and only if there is no edge between $X$ and $Y$.

Let $M_{\text{global}}(\mathcal G)$ bet the set of distributions which satisfy the global Markov property: thus $\mathbb P\in M_{\text{global}}(\mathcal G)$ if under $\mathbb P$, $A\perp \!\!\! \perp B|C$ if and only if $C separates $A$ and $B$

Finally in a graph $\mathcal G$ $M_{\text{pair}}(\mathcal G)=M_{\text{global}}(\mathcal G)$

This allows us to construct graphs using the simpler pairwise property and then we can deduce other independence relations using the global Markov property. Think how hard this would be to do algebraically. 



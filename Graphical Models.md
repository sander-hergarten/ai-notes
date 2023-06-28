Graphical models are a class of multivariate statistical models that are useful for representing independence relations. They are also useful to develop parsimonious models for multivariate data.

To see why parsimonious models are useful in the multivariate setting consider the problem of estimating the joint distribution of several discrete random variables. Two binary variables $Y_1$ and $Y_2$ can be represented as a two by two table which corresponds to a multinomial with four categories. Similarly, $k$ binary variables $Y_1,...,Y_k$ corresponds to a multinomial with $N=2^k$ categories.

When $k$ is even moderately large, $N=2^k$ will be huge. It can be shown in that case that the [[Parametric Inference#Maximum Likelihood|MLE]] is a poor estimator. The reason is that the data are sparse: there are not enough data to estimate so many parameters. Graphical models often require fewer parameters and may lead to estimators with smaller risk. 

There are two main types of [[Graphs|graphical models]]: 
- Undirected 
- Directed

An undirected graph example is the [[Pairwise Markov Graphs]]

# Separoid Definition

Let $M$ be a set with elements of the form $\langle A,B|C\rangle$ where $A,B,C$ are subset of a finite set $V$ (that is, $M$ is a ternary relation on $V$). Then $M$ is a separoid if it satisfies the following properties:
1. $\langle A,B|A\rangle \in M$
2. If $\langle A,B|C\rangle\in M$, then $\langle B, A|C\rangle \in M$ 
3. If $\langle A,B|C\rangle\in M$ and $D\subseteq A$, then $\langle D,B|C\rangle\in M$
4. If $\langle A,B|C\rangle\in M$ and $D\subseteq A$, then $\langle A,B|C\cup D\rangle\in M$
5. If $\langle A, B|C\rangle\in M$ and $\langle A,D|B\cup C\rangle\in M$, then $\langle A, B\cup D|C\rangle\in M$ 
For a more general construction refer to: 
	separoids: a mathematical framework for conditional independence and irrelevance”. Annals of Mathematics and Artificial Intelligence 32(1-4). Representations of uncertainty, 335–372. doi:
	10.1023/A:1016734104787. MR1859870.

for each vertex $v\in V$, we define a random variable $X_v$ on a sample space $\mathcal X_v$. Furthermore, for any $A\subseteq V$ we write the vector $X_A=(X_v)_{v\in V}$, the product space $\mathcal X_A=\prod_{v\in A}\mathcal X_v$, and $X=X_V$ and $\mathcal X=X_V$ 

 joint distribution $P$ for $X$ is Markov with respect to a separoid $M$ if :
 $$\langle A, B|C\rangle\in M\quad\Rightarrow X_A\perp\!\!\!\perp X_B|X_C$$

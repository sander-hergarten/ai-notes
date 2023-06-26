Loglinear models are useful for modelling multivariate discrete data. 

## The Loglinear Model
Let $X=(X_1,...,X_m)$ be a random vector with probability function 
$$f(x)=\mathbb P(X=x)=\mathbb P(X_1=x_1,...,X_m=x_m)$$
where $x=(x_1,...,x_m)$. Let $r_j$ be the number of values that $X_j$ takes. Without loss of generality, we can assume that $X_j\in\{0,1,...,r_j-1\}$. Suppose now that we have $n$ such random vectors. We can think of the data as a sample from a Multinomial with $N=r_1\times  r_2\times...\times r_m$ categories. THe data can be represented as counts in a $r_1\time
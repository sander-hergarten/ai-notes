Graphical models are a class of multivariate statistical models that are useful for representing independence relations. They are also useful to develop parsimonious models for multivariate data.

To see why parsimonious models are useful in the multivariate setting consider the problem of estimating the joint distribution of several discrete random variables. Two binary variables $Y_1$ and $Y_2$ can be represented as a two by two table which corresponds to a multinomial with four categories. Similarly, $k$ binary variables $Y_1,...,Y_k$ corresponds to a multinomial with $N=2^k$ categories.

When $k$ is even moderately large, $N=2^k$ will be huge. It can be shown in that case that the [[Parametric Inference#Maximum Likelihood|MLE]] is a poor estimator. The reason is that the data are sparse: there are not enough data to estimate so many parameters. Graphical models often require fewer parameters and may lead to estimators with smaller risk. 

There are two main types of [[Graphs|graphical models]]: 
- Undirected 
- Directed

An undirected graph example is the [[Pairwise Markov Graphs]]



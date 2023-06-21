We want to assign a real number $\mathbb{P}(A)$ to every [[Sample Spaces and Events|event]] $A$, called the probability of $A$. We also call $P$ a probability distribution or a probability measure. To qualify as a probability, $P$ has to satisfy three axioms:
>[!abstract] Definition 2.5
>A function $\mathbb{P}$ that assigns a real number $\mathbb{P}(A)$ to each event $A$ is a probability distribution or a probability measure if it satisfies the following three axioms:
>1. $\mathbb{P}(A)\ge0$ for  every $A$
>2. $\mathbb{P}(\Omega) = 1$
>3. if $A_1,A_2,...$ are disjoint then $$\mathbb{P}\left(\bigcup^{\infty}_{i=1}A_i\right)=\sum^{\infty}_{i=1}\mathbb{P}(A_i)$$

## Interpretations
There are many interpretations of $\mathbb{P}(A)$. The two common interpretations are frequencies and degrees of beliefs.

The degrees of belief interpretation says that the Probability measures the observers strength to believe that event $A$ occurs

the frequencies interpretation you say how often in relation to the over events the event $A$ will occur

## Misc. Properties
One can derive many properties of $\mathbb{P}$ from the axioms:
$$\begin{align}
\mathbb{P}(\emptyset)&&=&&0\\
A\subset B&&\Longrightarrow &&\mathbb{P}(A)\le\mathbb{P}(B)\\
0\le&&\mathbb{P}(A)&&\le1\\
\mathbb{P}(A^c)&&=&&1-\mathbb{P}(A)\\
A\bigcap B=\emptyset&&\Longrightarrow &&\mathbb{P}\left(A\bigcup B\right)\\
\end{align}$$
A less obvious property is given in the following lemma:
> [!quote] Lemma 2.6
> For any events $A$ and $B$, $\mathbb{P}(A\bigcup B)=\mathbb{P}(A)+\mathbb{P}(B)-\mathbb{P}(AB)$

We can also show:
> [!quote] Theorem 2.8
> If $A_n\rightarrow A$ then $\mathbb{P}(A_n)\rightarrow \mathbb{P}(A)$ as $n\rightarrow \infty$ 
> 

# Probability in Finite Sample Spaces
## Uniform Probability distribution
If $\Omega$ is finite and if each outcome is equally likely, then:
$$\mathbb{P}(A)=\frac{|A|}{|\Omega|}$$
## n choose k
Given $n$ objects, the number of ways of ordering these objects if $n!$. For convenience we define $0!=1$. we also define:
$$\binom{n}{k}=\frac{n!}{k!(n-k)!}$$
read "$n$ choose $k$", which is the number of distinct ways of choosing $k$ objects from $n$. For example if we have a class of 20 people and we want to select a committee of 3 students, then there are
$$\binom{20}{3}=\frac{20!}{3!17!}=1140$$
possible committees. we note the following:
$$\binom{n}{0}=\binom{n}{n}=1\quad \text{and}\quad\binom{n}{k}=\binom{n}{n-k}$$
## Independent  Events
The formal definition of independence is:
> [!abstract] Definition 2.9
> Two events $A$ and $B$ are independent if
> $$\mathbb{P}(AB)=\mathbb{P}(A)\mathbb{P}(B)$$
> and we write $A \perp \!\!\! \perp B$. A set of events $\{A_i:\ i\in I\}$ is independent if
> $$\mathbb{P}\left(\bigcap_{i\in J} A_i\right)=\prod_{i\in J}\mathbb{P}(A_i)$$
> for every finite subset $J$ of $I$


Suppose that $A$ and $B$ are disjoint events, each with positive probability. Can they be independent? No. This follows since $\mathbb{P}(A)\mathbb{P}(B)>0$ yet $\mathbb{P}(AB)=\mathbb{P}(\emptyset)=0$

> [!info] Summary
> 1. $A$ and $B$ are independent if $\mathbb{P}(AB)=\mathbb{P}(A)\mathbb{P}(B)$.
> 2. Independence is sometimes assumed and sometimes derived
> 3. Disjoint events with positive probability are not independent

## Conditional Probability
Assuming that $\mathbb{P}(B) > 0$, we define the conditional probability of $A$ given that $B$ has occured as follows.
>[!abstract] Defintion 2.12
>If $\mathbb{P}(B)>0$ then the conditional probability of $A$ given $B$ is 
>$$\mathbb{P}(A|B)=\frac{\mathbb{P}(AB)}{\mathbb{P}(B)}$$

Think of $\mathbb{P}(A|B)$ as the fraction of times $A$ occurs among those in which $B$ occurs. 

Here are some facts about conditional probabilities. For any fixed $B$ such that $\mathbb{P}(B)>0$, $\mathbb{P}(\cdot|B)$ is a probability i.e. it satisfies the three axioms of probability

In particular, $\mathbb{P}(A|B)\ge0$, $\mathbb{P}(\Omega|B)=1$ and if $A_1,A_2<...$ are disjoint then $\mathbb{P}\left(\bigcup^{\infty}_{i=1}A_i|B\right)=\sum^{\infty}_{i=1}\mathbb{P}(A_i|B)$. But it is in general **not** true that $\mathbb{P}(A|B\bigcup C)=\mathbb{P}(A|B)+\mathbb{P}(A|C)$. The rules of probability apply to events on the left of the bar. In general it is **not** the case that $\mathbb{P}(A|B) =\mathbb{P}(B|A)$.  

If $A$ and $B$ are independent events then:
$$\mathbb{P}(A|B)=\frac{\mathbb{P}(AB)}{\mathbb{P}(B)}=\frac{\mathbb{P}(A)\mathbb{P}(B)}{\mathbb{P}(A)}=\mathbb{P}(A)$$
So another interpretation of independence is that knowing $B$ doesn't change the probability of $A$

From definition 2.12 we can determine $\mathbb{P}(AB)=\mathbb{P}(A|B)\mathbb{P}(B)$ and also $\mathbb{P}(AB)=\mathbb{P}(B|A)\mathbb{P}(A)$. This can be convenient to compute $\mathbb{P}(AB)$ when $A$ and $B$ are not independent.

## Bayes' Theorem
>[!quote] Theorem 2.15 (The Law of Total Probability)
>Let $A_1,...,A_k$ be a partition of $\Omega$. Then, for any event $B$, $\mathbb{P}(B)=\sum^K_{i=1}\mathbb{P}(B|A_i)\mathbb{P}(A_i)$

Since $\mathbb{P}(BA_j)=\mathbb{P}(B|A_j)\mathbb{P}(A_j)$ from the definition of conditional probability.

>[!quote] Theorem 2.16 (Bayes' Theorem)
>Let $A_1,...,A_k$ be a partition of $\Omega$ such that $\mathbb{P}(A_i)>0$ for each $i$. If $\mathbb{P}(B)>0$ then, for each $i=1,..,k,
>>[!abstract] Definition
>>$$\mathbb{P}(A_i|B)=\frac{\mathbb{P}(B|A_i)\mathbb{P}(A_i)}{\sum_j\mathbb{P}(B|A_j)\mathbb{P}(A_j)}$$ 

we call $\mathbb{P}(A_i)$ the prior probability of $A$ and $\mathbb{P}(A_i|B)$ the posterior probability of $A$ 


## Sigma-Algebra
Generally it is not feasible to assign probabilities to all subsets of a sample space $\Omega$. Instead one restricts attention  to a set of events called a $\sigma$-algebra or a $\sigma$-field which is a class $\mathcal{A}$ that satisfies:
1. $\emptyset\in \mathcal A$
2. if $A_1, A_2,...,\in\mathcal A$ then $\bigcup^{\infty}_{i=1}A_i\in\mathcal A$ 
3. $A\in\mathcal A$ implies that $A^c\in\mathcal A$ 
The sets in $A$ are said to be measurable. we call ($\Omega,\mathcal A$) a measurable space. 

If $P$ is a probability measure defined on $\mathcal A$ then ($\Omega, \mathcal A, P$) is called a probability space. 

When  $\Omega$ is the real line, we take $\mathcal A$ to be the smallest $\sigma$-field that contains all the open subsets, which is called the Borel $\sigma$-field
The sample space $\Omega$ is the set of possible outcomes of an experiment. Points $\omega$ in $\Omega$ are called sample outcome or realizations. Events are subsets of $\Omega$.

Given an event $A$, let $A^c=\{\omega\in\Omega;\omega\notin A\}$  or informally: $A^c$ is an event that contains all of the realizations that do not appear in $A$

The complement of $\Omega$ is the empty set $\emptyset$. The union of events $A$ and $B$ is defined as $A\bigcup B =\{\omega \in \Omega;\ \omega\in A\ \text{or}\ \omega\in b\   \text{or}\ \omega \in \text{both}\}$ 
Which can be thought of as  $A$ or $B$. If $A_1,A_2,...$ is a sequence of sets then 
$$\bigcup^{\infty}_{i=1}A_i=\{\omega\in\Omega:\ \ \omega\in A_i\text{ for at least one }i\}$$
The intersection of $A$ and $B$ is written as the set intersection and means $A$ and $B$ informally.  If $A_1,A_2,...$ is a sequence of sets then 
$$\bigcap^{\infty}_{i=1}A_i=\{\omega\in\Omega:\ \ \omega\in A_i\text{ for all }i\}$$

Let $A-B=\{\omega:\ \omega\in A,\omega\notin B\}$. If every element of $A$ is also contained in $B$ we write $A\subset B$ or equivalently, $B\supset A$. If $A$ is a finite set, et $|A|$ denote the number of elements in $A$
![[Pasted image 20230618193404.png]]

We say that $A_1,A_2,...$ are disjoint or are mutually exclusive if $A_i\cap A_j=\emptyset$  whenever $i\ne j$. A partition of $\Omega$ is a sequence of disjoint sets $A_1,A_2, ...$ such that the union over the sequence gives omega. Given an event $A$, define the indicator functions of A by
$$I_A(\omega)=I(\omega\in A)=\begin{cases}1\quad\text{if } \omega\in A\\0\quad\text{if }\omega\notin A\end{cases}$$
A sequence of sets $A_1, A_2, ...$ is monotone increasing if $A_1\subset A_2\subset ...$ and we define $\lim_{n\rightarrow\infty}\ A_n=\bigcup^{\infty}_{i=1}A_i$   

![[Pasted image 20230618194630.png]]

---
tags:
- math/set-theory
- ruff-note
---

# Introduction 
Set Theory is the true study of infinity. This alone assures the subject of a place prominent in human culture. But even more, Set Theory is the milieu in which mathematics take place today. As such, it is expected to provide a firm foundation for the rest of mathematics. And it does-up to a point; we will prove theorems shedding light on this issue

Although Elementary Set Theory is well-known and straightforward, the modern subject, Axiomatic Set Theory, is both conceptually more difficult and more interesting. Complex issues arise in Set Theory more than any other area of pure mathematics; in particular, Mathematical Logic is used in a fundamental way.

## Richards Paradox
In order to introduce one of the thorny issues, let's consider the set of all those numbers which can be easily described, say in fewer then twenty English words. This leads to something called Richard's Paradox. The set
$$\set{x:\text{$x$ is a number which can be descirbed in fewer than 20 words}}$$
must be finite since there are only finitely many English words. Now, there are infinitely many counting numbers (i.e., the Natural numbers) and so there must be infinitely many counting numbers which are not in our set. So there is a smallest counting number which is not in the set. This number can be uniquely described as "the smallest counting number which cannot be described in fewer than twenty English words". Count this description-14 words. So the number must be *in* the set. But it can't be in the set. That's a contradiction. 

Our naive intuition about sets is wrong here. Not every collection of numbers with a description is a set. In fact it would be better to stay away from using languages like English to describe sets, one such. Our first task will be to build a new language for describing sets, one in which such contradictions cannot arise.

We also need to clarify exactly what is meant by "set". What is a set? We do not know the complete answer to this question. Many problems are still unsolved simply because we do not know whether or not certain objects constitute a set or not. Most of the proposed new axioms for Set Theory are of this nature.

# Notation
The atomic formulas are strings of symbols of the form:
$$(v_i\in v_j)\text{ or }(v_i=v_j)$$
The collection of formulas of set theory is defined as follows:
1. An atomic formula is a formula
2. If $\Phi$ is any formula, then $(\neg \Phi)$ is also a formula.
3. If $\Phi$ and $\Psi$ are formulas, then $(\Phi\vee\Psi)$ is also a formula
4. If $\Phi$ and $\Psi$ are formulas, then $(\Phi\rightarrow\Psi)$ is also a formula
5. If $\Phi$ and $\Psi$ are formulas, then $(\Phi\leftrightarrow\Psi)$ is also a formula
6. If $\Phi$ is a formula and $v_i$ is a variable, then $(\forall v_i)\Phi$ is also a formula
7. If $\Phi$ is a formula and $v_i$ is a variable, then $(\exists v_i)\Phi$ is also a formula

Furthermore, any formula is built up this way from atomic formulas and a finite number of applications of the inferences $2$ through $8$

### Subformulas
The Complete collection of subformulas of a formula $\Phi$ is defined as follows:
1. $\Phi$ is a subformula of $\Phi$
2. If $(\neg \Psi)$ is a subformula of $\Phi$, then so is $\Psi$ 
3. If $(\Theta \wedge \Psi)$ is a subformula of $\Phi$, then so are $\Theta$ and $\Psi$
4. If $(\Theta \vee \Psi)$ is a subformula of $\Phi$, then so are $\Theta$ and $\Psi$
5. If $(\Theta \rightarrow \Psi)$ is a subformula of $\Phi$, then so are $\Theta$ and $\Psi$
6. If $(\Theta \leftrightarrow \Psi)$ is a subformula of $\Phi$, then so are $\Theta$ and $\Psi$
7. If $(\forall v_i)\Psi$ is a subformula of $\Phi$ and $v_i$  is a variable, Then $\Psi$ is a subformula of $\Phi$
8. f $(\exists v_i)\Psi$ is a subformula of $\Phi$ and $v_i$  is a variable, Then $\Psi$ is a subformula of $\Phi$
Note that the subformulas of $\Phi$  are those formulas used in the construction of $\Phi$ 

### Bound Variables
To say that a variable $v_i$ occurs bound in a formula $\Phi$ means one of the following two conditions holds:
1. For some subformula $\Psi$ of $\Phi$, $(\forall v_i)\Psi$ is a subformula of $\Phi$ or
2. For some subformula $\Psi$ of $\Phi$, $(\exists v_i)\Psi$ is a subformula of $\Phi$

### Atomic Formulas 
The result, $\Phi^*$, of substituting the variable $v_j$, for each bound occurrence of the variable $v_i$, in the formula $\Phi$ is defined by constructing a $\Psi^*$ for each subformula $\Psi$ of $\Phi$ as follows:
1. If $\Psi$ is atomic, then $\Psi^*$ is $\Psi$ 
2. If $\Psi$ is $(\neg \Theta)$ for some formula $\Theta$, then $\Psi^*$ is $(\neg\Theta^*)$ 
3. If $\Psi$ is $(\Gamma\wedge \Theta)$ for some formula $\Theta$, then $\Psi^*$ is $(\Gamma^*\wedge\Theta^*)$ 
4. If $\Psi$ is $(\Gamma\vee \Theta)$ for some formula $\Theta$, then $\Psi^*$ is $(\Gamma^*\vee\Theta^*)$ 
5. If $\Psi$ is $(\Gamma\rightarrow \Theta)$ for some formula $\Theta$, then $\Psi^*$ is $(\Gamma^*\rightarrow\Theta^*)$ 
6. If $\Psi$ is $(\Gamma\leftrightarrow \Theta)$ for some formula $\Theta$, then $\Psi^*$ is $(\Gamma^*\leftrightarrow\Theta^*)$ 
7. If $\Psi$ is $(\forall v_k)\Theta$ for some formula $\Theta$ then $\Theta^*$ is just $(\forall v_k)\Theta^*$ if $k\neq i$, but if $k=i$ then $\Psi^*$ is $(\forall v_j)\Gamma$ where $\Gamma$ is the result of substituting $v_j$ for each occurrence of $v_i$ in $\Theta$ 
8. If $\Psi$ is $(\exists v_k)\Theta$ for some formula $\Theta$ then $\Theta^*$ is just $(\forall v_k)\Theta^*$ if $k\neq i$, but if $k=i$ then $\Psi^*$ is $(\exists v_j)\Gamma$ where $\Gamma$ is the result of substituting $v_j$ for each occurrence of $v_i$ in $\Theta$ 

## Free Variables
That a variable $v_i$ occurs free in a formula $\Phi$ means that at least one of the following is true:
1. $\Phi$ is an atomic formula and $v_i$ occurs in $\Phi$ 
2. $\Phi$ is $(\neg \Psi)$, $\Psi$ is a formula and $v_i$ occurs free in $\Psi$ 
3. $(\Theta \wedge \Psi)$ , $\Theta$ and $\Psi$ are formulas and $v_i$ occurs free in $\Theta$ or occurs free in $\Psi$ 
4. $\Psi$ is $(\Theta)$
5. ...

As in the example below, a variable can occur both free and bound in a formula. However, notice that if a variable occurs in a formula at all it must occur either free, or bound, or both (but not at the same occurrence) 

We define the important notion of the substitution of a variable $v_j$ for each free occurrence of the variable $v_i$ in the formula $\Phi$. This procedure is as follows:

1. Substitute a new variable $v_1$ for all bound occurrences of $v_i$ in $\Phi$ 
2. Substitute another new variable $v_k$ for all bound occurrences of $v_j$ in the result of 1.
3. Directly substitute $v_j$ for each occurrence of $v_i$ in the result of 2.

> [!quote] Example
> Let us substitute $v_2$ for all free occurrences of $v_1$ in the formula 
> $$((\forall v_1)((v_1=v_2)\rightarrow(v_1\in v_0))\wedge (\exists v_2)(v_2\in v_1))$$
> The steps are as follows:
> 1. $((\forall v_1)((v_1=v_2)\rightarrow(v_1\in v_0))\wedge (\exists v_2)(v_2\in v_1))$
> 2.  $((\forall v_3)((v_3=v_2)\rightarrow(v_3\in v_0))\wedge (\exists v_2)(v_2\in v_1))$
> 3.  $((\forall v_3)((v_3=v_2)\rightarrow(v_3\in v_0))\wedge (\exists v_4)(v_4\in v_1))$
> 4. $((\forall v_3)((v_3=v_2)\rightarrow(v_3\in v_0))\wedge (\exists v_4)(v_4\in v_2))$

For the reader who is new to this abstract game of formal logic, step 2 in the substitution procedure may appear to be unnecessary. It is indeed necessary, but the reason is not obvious until we look again at the example to see what would happen if step 2. were omitted.  This step essentially changes $(\exists v_2)(v_2\in v_1)$ to $(\exists v_4)(v_4\in v_1)$. We can agree that each of these means the same thing namely $v_1$ is not empty. however, when $v_2$ is directly substituted into each we get something different:
$(\exists v_2)(v_2\in v_2)$ and $(\exists v_4)(v_4\in v_2)$. The latter says $v_2$ is not empty and this is of course what we would hope would be the result of substituting $v_2$ for $v_1$. The former statement seems quite different, making the strange assertion that $v_2$ is an element of itself.

Tis problem is caused by the variable $v_2$ becoming bound as a result of being substituted for $v_1$. We must ensure that freedom is preserved when substituting.


For a formula $\Phi$ and variables $v_i$ and $v_j$, let $\Phi(v_i|v_j)$ denote the formula which results from substituting $v_j$ for each free occurrence of $v_i$. In order to make $\Phi(v_i|v_j)$ well defined, we insist that in steps 1 and 2 of the substitution process, the first new variable available is used. Of course the use of any other new variable gives an equivalent formula. In the example, if $\Phi$ is the formula on the first line, then $\Phi(v_1|v_2)$ is the formula on the fourth line.

As a simple application we can show how to express "there exists a unique element". For any formula $\Phi$ of the language of set theory we denote by $(\exists!v_j)\Phi$ the formula
$$((\exists v_j)\Phi \wedge (\forall v_j)(\forall v_l)((\Phi\wedge\Phi(v_j|v_l))\rightarrow(v_j=v_l)$$
where $v_l$ is the first available variable which does not occur in $\Phi$. The expression $(\exists!v_j)$ can be considered as an abbreviation in the language of set theory, that is, an expression which is not actually part of the language. However, whenever we have a formula containing this expression, we can quickly convert it to a proper formula of the language of set theory.

## Classes
A class is just a string of symbols of the form $\set{v_i\ :\ \Phi}$ where $v_i$ is a variable and $\Phi$ is a formula. Two important and well-known examples are:
$$\set {v_0:(\neg(v_0=v_0))}$$
which is called the empty set and is usually denoted $\emptyset$, and 
$$\set{v_0:(v_0=v_0)}$$
which is called the universe and is usually denoted by $\mathbb V$ 

## Terms
A Term is defined to be either a class or a variable. Terms are the names for what the language of set theory talks about. A grammatical analogy is that terms correspond to nouns and pronouns, classes to nouns, and variables to pronouns. Continuing the analogy, the predicates, or verbs, are $=$ and $\in$. The atomic formulas are the basic relationships among the predicates and the variables


We can incorporate classes into the language of set theory by showing how the predicates relate to them. Let $\Psi$ and $\Theta$ be formulas of the language of set theory and let $v_j$, $v_k$ and $v_l$ be variables. We write:
![[Pasted image 20230723170423.png]]
whenever $v_l$ is neither $v_j$ nor $v_k$ and occurs in neither $\Psi$ not $\Theta$ 

## Substituting Classes
We can now show how to express, as a proper formula of set theory, the substitution of a term $t$ for each free occurrence of the variable $v_i$ in the formula $\Phi$. We denote the resulting formula  of set theory by $\Phi(v_i|t)$. The case when $t$ is a variable $v_j$ has already been discussed. Now we turn our attention to the case when $t$ is a class $\set{v_j:\Psi}$ and carry out a procedure  similar to the variable case:
1. Substitute the first available new variable for all bound occurrences of $v_i$ in $\Phi$.
2. In the result of 1, substitute, in turn, the first available new variable for all bound occurrences of each variable which occurs free in $\Psi$
3. In the result of 2, directly substitute $\set{v_j:\Psi}$ for v_i into each atomic subformula in turn, using the table above.
For example, the  atomic subformula $(v_i\in v_k)$ is replaced by the new subformula
$$(\exists v_l)((v_l\in v_k)\wedge(\forall v_j)((v_j\in v_l)\leftrightarrow \Psi))$$
where $v_l$ is the first available new variable. Likewise, the atomic subformula $(v_i=v_i)$ is replaced by the new subformula 
$$(\forall v_l)(\Psi(v_j|v_l)\leftrightarrow\Psi(v_j|v_l))$$
where $v_l$ is the first available new variable (although it is not important to change from $v_j$ to $v_l$ in this particular instance)


Since the language of set Theory is very precise we need to find a way to make these formulas more intelligible. 

In order to avoid inconsistencies associated with Richard's paradox we must ensure the the formula $\Phi$ in the class $\set{v_j:\Phi}$ is indeed a proper formula of the language of set theory, or at least can be converted to a proper formula once the abbreviations are eliminated. It is not so important that we actually write classes using proper formulas, but what is important is that whatever formula we write down can be converted into a proper formula by eliminating abbreviations and slang.

We can now relax our formalism is we keep the previous paragraph in mind. Let's adopt these conventions.
1. We can use any letters that we like for varaibles
2. We can freely omit parentheses and sometimes use brackets instead
3. We can write out "and" for "$\wedge$", "or" for "$\vee$", "implies" for "$\rightarrow$" and use the "if then" format as well as other common English expressions for the logical connectives and quantifiers.
4. We will use the notation $\Phi(x,y,w_1,...,w_k)$ to indicate that all free variables of $\Phi$ lie among $x,y,w_1,...,w_k$. When the context is clear we use the notation $\Phi(x,t,w_1,...,w_k)$ for the result of substituting the term $t$ for each free occurrence of the variable $y$ in $\Phi$, i.e., $\Phi(y|t)$ 
5. We can write out formulas, including statements of theorems, in any way easily seen to be convertible to a proper formula in the language of set theory.

For any terms $r,s,t$ we can make the following abbreviations of formulas.
![[Pasted image 20230723175230.png]]
Whenever we have a finit number of terms $t_1,t_2,...,t_n$ the notation $



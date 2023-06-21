(https://www.cs.cmu.edu/~osogami/thesis/html/node39.html)

## Examples
An [[Exponential Distribution]] is a PH distribution. Second a [[Convolution]] of two independent identical exponential distributions is a PH distribution. This is called an Erlang-2 distribution. Third a mixture distribution between 2 exponential distribution is also a PH distribution

# Definition 
In general, a PH distribution is the distribution of the time until absorption into state 0 in a Markov chain. 

# Subclasses of PH distribution 
By restricting the structure of the Markov chain , we can define a subclass of the PH distribution. 

## Acyclic Ph distribution
First if the Markov chain whose absorption time  defines a PH distribution is acyclic the PH distribution is called an acyclic PH distribution. 
![[Pasted image 20230603160804.png]]

## Coxian PH distribution
An acyclic PH distribution is called Coxian PH distribution if the Markov chain, whose absorption time defines the acyclic PH distribution, has the following two properties: 
1. the initial non-absorbing state is unique (i.e. the initial state is either the unique non absorbing state or the absorbing state) 
2. for each state, the next non-absorbing state is unique (i.e. the next state is the unique non-absorbing state or the absorbing state)
![[Pasted image 20230603160817.png]]
When a Coxian PH distribution does not have mass probability at zero(i.e. the initial state is not the absorbing state), we refer to the Coxian PH distribution as a Coxian$^+$ PH distribution.

## Hyperexponential distribution
AN acyclic PH distribution is called a hyperexponential distribution if  the Markov chain whose absorption time defines the acyclic PH distribution has the following property: for any state, the next state is the absorbing state. That is, a mixture of exponential distributions is a hyperexponential distribution.

## Erlang Distribution
An acyclic PH distribution is called an Erlang distribution if the Markov chain whose absorption time defines the acyclic distribution has following properties:
1. the initial state is a unique non-absorbing state
2. for each state the next state is unique
3. the [[Sojourn Time]] distribution at each state is identical
That is, the sum of $n$ independent and identically distributed exponential random variables has an $n$-phase Erlang distribution. An $n$-phase Erlang distribution is also called an Erlang-$n$ distribution. 

### Generalised Erlang Distribution
An Erlang distribution is generalised to a generalised Erlang distribution by allowing a transition from the initial state to the absorbing state.
![[Pasted image 20230603164332.png]]

### Mixed Erlang Distribution
A mixture of Erlang distributions is called a mixed Erlang distribution. A mixture of Erlang distributions with the same number of phases is called a mixed Erlang distribution with common order.
![[Pasted image 20230603164344.png]]

# Properties of HP distributions
The 
---
tags: math/statistics
---
(https://towardsdatascience.com/an-intuitive-look-at-fisher-information-2720c40867d8)
# Intuition 
The Likelihood is best explained by an example 

assume a [[Poisson Distribution|Poisson process]] that models the number of patient arrivals per hour at the ER of a hospital

In this data sample, the random variable $Y$ is the count of patient arrivals per hour. Since $Y$ is a discrete random variable, it must obey some [[Probability Mass Function (PMF)|PMF]]. 

Now Suppose you observe a certain number of patients walking into the ER during a particular hour. Suppose $y=10\in Y$. 

Since the Poisson probability is dependent on Parameter $\lambda$ which in this context describes the unknown mean event rate, we can allow this value to vary while keeping our random variable the same. 

![[Pasted image 20230623194324.png]]
(Smoothed Poisson distribution for $\lambda =16$)

We are asking the question:"what is the probability of observing 10 events in some unit time interval, given different values of the mean rates $\lambda$"

![[Pasted image 20230623194435.png]]

In the Plot above the X-axis describes the value of parameter $\lambda$. The Y-axis depicts what's know as the Likelihood function of $\lambda$. It is read off as the Likelihood of $\theta$ for a given observed value of the random variable $y$.

# Definition
>[!abstract] Definition
>The likelihood function is defined by 
>$$\mathcal L_n(\theta)=\prod^n_{i=1}f(X_i;\theta)$$
>The log-likelihood function is defined by $\mathcal l_n(\theta)=\log\mathcal L_n(\theta)$


for $N_1(x_1;g(Y))$ where $Y=N_2(x_2;\theta)$ and $N_1, N_2$ both describe the PDF of a normal distribution,  how do i calculate a factor that is proportional to the causal effect of $\theta$ 


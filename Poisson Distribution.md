A Poisson distribution is a discrete probability distribution that expresses the probability of a given number of events ocuring in a fixed interval 
# Definition
PMF:
$$\frac{\lambda^ke^{-\lambda}}{k!}$$
CDF:
$$Q(\lfloor k+1\rfloor)=\frac{\Gamma(\lfloor k+1\rfloor,\lambda)}{\lfloor k\rfloor!}=e^{-\lambda}\sum^{\lfloor k\rfloor}_{j=0}\frac{\lambda^j}{j!}$$
for $k\ge0$, where $\Gamma(x,y)$ is the [[Incomplete Gamma Functions|upper incomplete Gamma function]] and $Q$ is the [[Incomplete Gamma Functions|regularized gamma function]]


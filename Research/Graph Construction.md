## TODO 
- [ ] proving $a=b\quad \forall a,b\quad a\subset M,b\subset N\Rightarrow M=N$   (easy)
- [ ] proving $a=b$ for "rough" states
- [ ] extract information out of weak states
- [ ] proving convergence to a minimal apg through iteration.
- [ ] proving showing there is a minimal apg for all $S$
- [ ] showing time complexity of algorithm
- [ ] develop algorithm for clean states
- [ ] Proving that continuous state spaces get minimized into finite state spaces (🙃)

weak states are states that are not fully developed due to training

rough states are states where not all information is present to predict the next state. As such they are distributed

clean sates are the perfect deterministic states we would like to have

two states are equal if there exists a bisimulation between them i.e. that both states have an equivalent decoration. 

## Extras
- [ ] Fast equality check of elements calculation

# Model 
$$\mathcal E =(A,\mathcal T, \mathcal O)$$
$A = \set{\text{set of all actions}}$
$s_{n}, r = \mathcal{T}(s_{n-1}, a)$
$s_{a} = s_{b}\Rightarrow \mathcal T(s_{a-1},a) = \mathcal T(s_{b-1}, a)$ 

# Model Interpreter
$$\mathcal E  = (A, \mathcal T_{\mathcal{O}^{-1}})$$




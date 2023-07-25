---
tags:
- finance
---
![[Pasted image 20230622020627.png]] 

It makes a set of assumptions, including that markets are efficient, returns are normally distributed, and that there are no transaction costs. 



**Binomial Option Pricing Model**

The binomial option pricing model is a simpler model that calculates the value of an option by creating a binomial tree to represent possible paths the price of the underlying asset can take over the life of the option. This model is often used for American options which can be exercised at any time before expiration, unlike European options which can only be exercised at expiration.

The model involves three steps:

1. **Create the binomial price tree**: The model starts with the current price of the asset, and each time period is represented by a node in the tree. Each node then branches into two possible outcomes for the next time period (an up movement or a down movement).
    
2. **Calculate option value at each final node**: At each final node of the tree—i.e., at expiration of the option—the option value is simply its intrinsic value: for a call option, this is max((S-X), 0), and for a put option, max((X-S), 0), where X is the strike price and S is the spot price.
    
3. **Iterate backwards through the tree**: For American options, at each node the option value is calculated as the greater of its intrinsic value or the present value of the expected option value from the next period. For European options, you do not consider the intrinsic value at each node, only the expected option value from the next period. 

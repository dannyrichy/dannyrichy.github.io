---
layout: default
title: Wiener Process
category: "Prob thingies"
---
## Wiener Process

Date: 19/11/2024

#### Whazzat!

A weiner process $$ W_t $$ has the following properties 
 - $$ W_0 = 0 $$, it always is assumed to start from 0. 
 - $$ W_t $$ is ***almost surely*** continous. An event happening almost surely means it happens _with probability 1_
 - Increaments are independent of each other
 - $$ W_t - W_s \sim \mathcal{N}(0, t-s) \| \forall 0 \leq s \leq t  $$. 
  

<video controls>
  <source src="https://upload.wikimedia.org/wikipedia/commons/transcoded/a/a9/2D_Random_Walk_400x400.ogv/2D_Random_Walk_400x400.ogv.360p.vp9.webm" type="video/webm">
  Your browser does not support the video tag.
</video>

A weiner process can also be defined as the integral of [white noise generalized Gaussian process](https://en.wikipedia.org/wiki/White_noise#Continuous-time_white_noise). Thus, weiner process is not stationary but its increments are. 

#### Uses

Weiner process are used to model **Stochastic Differential Equation**. For example [Ornstein–Uhlenbeck process](https://en.wikipedia.org/wiki/Ornstein%E2%80%93Uhlenbeck_process) is stochastic process that is both [Gaussian process](/notes/gaussian-process.html) and [Markov process](/notes/markov-process.html). It is given by the following stochastic differential equation

$$
dx_t = \theta(\mu - x_t) dt + \sigma dW_t
$$

where $$ \theta ,\sigma \gt 0 $$. This is used to model *stochastic gradient descent*, where samples are assumed to be *i.i.d*

#### Further reading
- [Brownian bridge](https://en.wikipedia.org/wiki/Brownian_bridge)

#### Interesting tid-bits

    " Observe what happens when sunbeams are admitted into a building and shed light on its shadowy places. You will see a multitude of tiny particles mingling in a multitude of ways... their dancing is an actual indication of underlying movements of matter that are hidden from our sight... It originates with the atoms which move of themselves [i.e., spontaneously]. Then those small compound bodies that are least removed from the impetus of the atoms are set in motion by the impact of their invisible blows and in turn cannon against slightly larger bodies. So the movement mounts up from the atoms and gradually emerges to the level of our senses so that those bodies are in motion that we see in sunbeams, moved by blows that remain invisible." - Lucretius 



#### References
- [https://galton.uchicago.edu/~lalley/Courses/313/BrownianMotionCurrent.pdf](https://galton.uchicago.edu/~lalley/Courses/313/BrownianMotionCurrent.pdf)
- [https://en.wikipedia.org/wiki/Brownian_motion](https://en.wikipedia.org/wiki/Brownian_motion)
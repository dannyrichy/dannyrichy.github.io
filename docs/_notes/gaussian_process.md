---
layout: default
title: Gaussian Process
category: "Prob thingies"
---

## Gaussian Process

Date: 9/11/2024

#### Whazzat!

**Stochastic Process**: A stochastic process is a set of random variables in a probability space. The index of which is usually time. More formally, given a probability space $$ (\Omega, \mathcal{F}, \mathcal{P}) $$, and an index set $$ \mathcal{T} $$, the stochastic process is $$ {X(t) \| t \in \mathcal{T}} $$. 

A [time continuous stochastic process](https://en.wikipedia.org/wiki/Continuous-time_stochastic_process), $$ {X(t) \| t \in \mathcal{T}} $$ where any finite set of indices $$ t_1, t_2, \cdots t_k \in \mathcal{T} $$ ensures that $$ X_{t_1, t_2, \cdots t_k} = [X(t_1), X(t_2), \cdots X(t_k)]^T $$ is a multivariate Gaussian random variable. 
    A multivariate Gaussian rv is same as saying any linear combination of $$ (X(t_1), X(t_2), \cdots X(t_k)) $$ is a univariate Gaussian distribution. 😲

- The variance of a Gaussian process is finite at any time t, i.e., $$ \mathbb{E}[\|X(t)-\mathbb{E}[X(t)]\|^2 ] \le \infty \forall t \in \mathcal{T} $$
- For Gaussian Stochastic process, __[strict sense stationarity](https://en.wikipedia.org/wiki/Stationary_process#strict-sense_stationarity)__ is equivalent to __[wide sense stationarity](https://en.wikipedia.org/wiki/Stationary_process#wide-sense_stationarity)__ .
- If a gaussian process is assumed to have mean zero, then it's behaviour is completely defined by the *covariance function*.

#### Covariance function
The covariance function should be non-negative definiteness which allows us to use Karhunen–Loève expansion. Choice of covariance function allows us to control *stationarity, isotropy, smoothness and periodicity*. A stationary process has covariance function between two points *x*, *x'* that depends only on *x-x'* . Furthermore, the process is isotropic if it only depends on the euclidean norm between them and not direction. 

    Another way of looking at covariance function is that we are choosing a prior over the function.

#### RKHS

**TODO**

#### Multivariate Gaussian Process

[Read](https://stats.stackexchange.com/questions/655537/creating-correlated-gaussian-processes)


#### Further reading
- [Karhunen–Loève expansion](https://en.wikipedia.org/wiki/Kosambi%E2%80%93Karhunen%E2%80%93Lo%C3%A8ve_theorem), used to spectrally decompose *covariance function* that yields the orthogonal basis such that the total mean squared error is minimized. Equivalent to **PCA**.  

#### _Questions_
- Since in the prelude, we say that the set of random variables is from the same probability space, does it mean that each $$ W_t $$ from [brownian motion](/notes/brownian-motion.html) is from Normal distribution ? 😵‍💫
  I don't think I understand what a probability space is, gotta understand that ***TODO***
---
### References
- [https://distill.pub/2019/visual-exploration-gaussian-processes/](https://distill.pub/2019/visual-exploration-gaussian-processes/)
- [https://en.wikipedia.org/wiki/Stochastic_process](https://en.wikipedia.org/wiki/Stochastic_process)
---
layout: default
title: KL divergence
category: "What the Bayes Is Going On?"
---
## Wiener Process

Date: 06/06/2025

#### Whazzat!

Kullback–Leibler divergence measures how much one probability distribution $$ \mathcal{Q} $$ is different from a true probability distribution (denoted by $$  \text{KL}(P\|Q) $$). It is a divergence measure and not a distance measure (meaning it is not symmetric). Thus $$  \text{KL}(P\|Q) ≠ KL(Q\|P) $$. 

#### Properties

- $$  \text{KL}(P\|Q) \geq 0 $$, equality holds *if and only if* $$ P = Q $$ as measures.

***Proof***

NOTE: $$ \log x \leq x - 1, \forall x \gt 0 $$. 

$$ \text{KL}(P\|Q) =  \int_{\mathcal{X}} p(x) \log(\frac{p(x)}{q(x)}) \,dx  $$
$$ = -  \int_{\mathcal{X}} p(x) \log(\frac{q(x)}{p(x)}) \,dx  $$
$$ \geq -   \int_{\mathcal{X}} p(x) (\frac{q(x)}{p(x)} - 1) \,dx = \int_{\mathcal{X}} p(x) \,dx - \int_{\mathcal{X}} q(x) \,dx = 0 $$
$$ \text{KL}(P\|Q) \geq 0 $$

- $$ KL(P(x,y)\|Q(x,y)) \geq KL(P(x)\|Q(x)) $$

***Proof***
$$ \text{KL}(P(x,y)\|Q(x,y)) = \int_{\mathcal{X}}\int_{\mathcal{Y}} p(x,y) \log(\frac{p(x,y)}{q(x,y)}) \,dx \,dy $$

$$ = \int_{\mathcal{X}}\int_{\mathcal{Y}} p(x \text{\textbar}  y) p(y) \log(\frac{p(x \text{\textbar} y)p(y)}{q(x\text{\textbar} y)q(y)}) $$

$$ = \int_{\mathcal{Y}}p(y) (\int_{\mathcal{X}} p(x \text{\textbar} y) \log(\frac{p(x\text{\textbar} y)}{q(x\text{\textbar} y)}) \,dx) \,dy  + \int_{\mathcal{Y}}p(y)\log(\frac{p(y)}{q(y)}) (\int_{\mathcal{X}} p(x\text{\textbar} y) \,dx) \,dy $$

$$ = \int_{\mathcal{Y}}p(y) \text{KL}(P(x\text{\textbar} y)) \,dy + \text{KL}(P(y)\|Q(y)) $$


$$ \text{KL}(P(x,y)\|Q(x,y)) \geq \text{KL}(P(y)\|Q(y)) $$


#### References
- [https://stats.stackexchange.com/questions/335197/why-kl-divergence-is-non-negative](https://stats.stackexchange.com/questions/335197/why-kl-divergence-is-non-negative)
- [https://stats.stackexchange.com/questions/483195/kullback-leibler-divergence-and-marginals](https://stats.stackexchange.com/questions/483195/kullback-leibler-divergence-and-marginals)
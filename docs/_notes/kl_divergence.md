---
layout: default
title: KL divergence
category: "What the Bayes Is Going On?"
mathjax: true
---
## Wiener Process

Date: 06/06/2025

#### Whazzat!

Kullback–Leibler divergence measures how much one probability distribution $$ \mathcal{Q} $$ is different from a true probability distribution (denoted by $$ KL(P\|Q) $$). It is a divergence measure and not a distance measure (meaning it is not symmetric). Thus $$ KL(P\|Q) ≠ KL(Q\|P) $$. 

#### Properties

- $$ KL(P\|Q) \geq 0 $$, equality holds *if and only if* $$ P = Q $$ as measures.

***Proof***

NOTE: $$ \log x \leq x - 1, \forall x \gt 0 $$. 

$$

\begin{aligned}
 \text{KL}(P\|Q) = \[ \int_{\mathcal{X}} p(x) \log(\frac{p(x)}{q(x)}) \,dx \]  \\
  &= -  \int_{\mathcal{X}} p(x) \log(\frac{q(x)}{p(x)}) \,dx  \\
  \geq -   \int_{\mathcal{X}} p(x) (\frac{q(x)}{p(x)} - 1) \,dx = \int_{\mathcal{X}} p(x) \,dx - \int_{\mathcal{X}} q(x) \,dx = 0 \\
  \text{KL}(P\|Q) &\geq 0
\end{aligned}

$$


#### References
- [https://stats.stackexchange.com/questions/335197/why-kl-divergence-is-non-negative](https://stats.stackexchange.com/questions/335197/why-kl-divergence-is-non-negative)
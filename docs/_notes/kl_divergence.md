---
layout: default
title: KL divergence
category: "What the Bayes Is Going On?"
---
## Wiener Process

Date: 06/06/2025

#### Whazzat!

Kullback–Leibler divergence measures how much one probability distribution $$ \mathcal{Q} $$ is different from a true probability distribution (denoted by $$ KL(P\|\|Q) $$). It is a divergence measure and not a distance measure (meaning it is not symmetric). Thus $$ KL(P\|\|Q) ≠ KL(Q\|\|P) $$. 

#### Properties

- $$ KL(P\|\|Q) \geq 0 $$, equality holds *if and only if* $$ P \eq Q $$ as measures.

***Proof***
NOTE: $$ ln x \leq x - 1, \forall x \gt 0 $$. 

Now, $KL( P \|\| Q) = ∫ p(x) log(\frac)


#### References
- [https://stats.stackexchange.com/questions/335197/why-kl-divergence-is-non-negative](https://stats.stackexchange.com/questions/335197/why-kl-divergence-is-non-negative)
---
layout: default
title: Dirichlet distribution
category: "What the Bayes Is Going On?"
---
## Dirichlet distribution

Date: 18/11/2024

#### Whazzat!

A dirichlet distribution is a multivariate generalisation of [beta distribution](https://en.wikipedia.org/wiki/Beta_distribution). Thus,,dirichlet distribution is used as conjugate prior for categorical distribution, just like how beta distribution is for [bernouilli](https://en.wikipedia.org/wiki/Bernoulli_distribution) and [binomial distribution](https://en.wikipedia.org/wiki/Binomial_distribution). It is parameterised by $$ \mathbf{\alpha} = [\alpha_1, \alpha_2,\cdots \alpha_n]^T $$. The following image is taken from [wiki](https://en.wikipedia.org/wiki/Dirichlet_distribution) where n = 3 and the $$ \alpha_1 = \alpha_2 = \alpha_3 $$.

![dir_img](https://upload.wikimedia.org/wikipedia/commons/thumb/5/54/LogDirichletDensity-alpha_0.3_to_alpha_2.0.gif/250px-LogDirichletDensity-alpha_0.3_to_alpha_2.0.gif)

To play with each $$ \alpha_i $$ [Click here](https://observablehq.com/@herbps10/dirichlet-distribution).

#### Density function

$$ 
\text{Dir}(x;\mathbf{\alpha}) = \frac{1}{B(\mathbf{\alpha})} \prod_{i=1}^{n} x_i^{\alpha_i-1} \\
B(\mathbf{\alpha}) = \frac{\prod_{i=1}^{n}\Gamma(\alpha_i)}{\Gamma(\alpha_0)} 
$$

The mean is given by $$ \mathbb{E}[X_i]==\frac{\alpha_i}{\alpha_0} $$, where $$ \alpha_0 = \sum_{i=1}^{n} \alpha_i $$.

#### Use cases

- Using **Dirichlet distribution** as means to sample a probability values for categorical distribution allows one to control heterogeneity. Fo instance having constant vector $$ \mathbf{\alpha} \approx 0 $$ would give highly heterogeneous sample as compared to $$ \mathbf{\alpha} \approx 10^6 $$. 

#### References
- [https://stephens999.github.io/fiveMinuteStats/dirichlet.html](https://stephens999.github.io/fiveMinuteStats/dirichlet.html)
- [https://en.wikipedia.org/wiki/Dirichlet_distribution](https://en.wikipedia.org/wiki/Dirichlet_distribution)
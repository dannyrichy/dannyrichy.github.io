---
layout: default
title: Dirichlet distribution
date: 2024-11-18
description: "A stochastic process which can be used to model distribution of functions"
---
<!-- Mathjax Support -->
<script type="text/javascript" async src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

## Dirichlet distribution

A dirichlet distribution is a multivariate generalisation of [beta distribution](https://en.wikipedia.org/wiki/Beta_distribution). Thus,,dirichlet distribution is used as conjugate prior for categorical distribution, just like how beta distribution is for [bernouilli](https://en.wikipedia.org/wiki/Bernoulli_distribution) and [binomial distribution](https://en.wikipedia.org/wiki/Binomial_distribution). 

It is parameterised by a vector \(\textbf{\alpha} = [\alpha_1, \alpha_2,\cdots \alpha_n]\)
---
layout: default
title: Gaussian Process
date: 2024-11-09
description: "A stochastic process which can be used to model distribution of functions"
---

## Gaussian Process

Date: 9/11/2024


A stochastic process where collection of n time points form a multi-variate Gaussian Distribution. This is used to model distribution of functions, as such that mean of the Multivariate distribution gives the mean function at these time instances. The covariance matrix is defined by kernel function that takes in x_t and x_{t+1} points and outputs the covariance value between them. There is only one constraint on the kernel function. It needs to be positive semi-definite functions.

---
layout: default
title: Mirror Descent
category: "In Too Deep (Learning)"
---
## Mirror Descent

Date: 26/11/2024

There are some hard-core maths background for convex optimization which I don't want to rehash off of these posts
- [Convex analysis part I](https://tlienart.github.io/posts/2018/09/23-convex-optimisation-1/){:target="_blank"}., [Convex analysis part II](https://tlienart.github.io/posts/2018/09/24-convex-optimisation-2/){:target="_blank"}., [Convex analysis part III](https://tlienart.github.io/posts/2018/10/09-convex-optimisation-3/){:target="_blank"}. It introduces notion of proper convex functions and lower semi-continuous functions. [Projected Gradient Descent](https://tlienart.github.io/posts/2018/10/10-projected-gradient-descent/index.html){:target="_blank"} which uses Euclidean projection on a convex set to find the minimizer.

#### Whazzat

    Mirror descent is a method for constrained optimization

Re-writing the Projected Gradient Descent method, we arrive at two terms inside the minimizer function. One term is $$ \frac{1}{\alpha_k}\frac{\|x-x_k\|^2_2}{2} $$, where k is the iteration step and $$ \alpha_k $$ is the learning step (I guess). If we generalize the Euclidean distance to any notion of distance, then we obtain a term which is like $$ \frac{1}{\alpha_k}\frac{d(x,x_k)}{2} $$, where $$ d : \mathbb{R}^n\times\mathbb{R}^n \rightarrow \mathbb{R}^{+}$$.

**WHY THOUGH?**: That's coz if we know the shape of the convex set, we can utilize that to better guide our minimizer

[https://tlienart.github.io/posts/2018/10/27-mirror-descent-algorithm/](https://tlienart.github.io/posts/2018/10/27-mirror-descent-algorithm/)

---
### References
- [T. Lienart's notes](https://tlienart.github.io/posts/){:target="_blank"}
- [Boyd's Lecture notes](https://see.stanford.edu/materials/lsocoee364b/01-subgradients_notes.pdf){:target="_blank"}
- [https://en.wikipedia.org/wiki/Mirror_descent](https://en.wikipedia.org/wiki/Mirror_descent){:target="_blank"}
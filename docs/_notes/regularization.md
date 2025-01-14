---
layout: default
title: Different view points of regularization
category: "In Too Deep (Learning)"
---
## How Regularization can be explained

Date: 14/01/2025

I came across this [tweet](https://x.com/andrew_n_carr/status/1875625454025240730) (or should I call it an "X post" now?) and found it both interesting and personally alarming—mainly because I couldn’t immediately recall what the KKT conditions are off the top of my head. So, this post is meant to help me revisit and brush up on some basic concepts.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Here&#39;s a great ML interview question: <br><br>First ask about regularization. The candidate will likely talk about norm penalties on weights.<br><br>Then ask &quot;why do we do lambda norm penalties, - lambda|w| , instead of directly constraining |w|&lt;R if they&#39;re essentially equivalent under…</p>&mdash; Andrew Carr (e/🤸) (@andrew_n_carr) <a href="https://twitter.com/andrew_n_carr/status/1875625454025240730?ref_src=twsrc%5Etfw">January 4, 2025</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

#### Whazzat
First, let me rephrase the question for clarity and brevity. The focus is on the $\lambda$ parameter in the optimization framework:

$$
\min_x \mathcal{L}(x; \theta) + \frac{\lambda}{2} \|x\|_2^2
$$

Here, $$ \mathcal{L}(x; \theta) $$ denotes the primary loss function (e.g., cross-entropy or mean squared error), and the second term represents the $$ L_2 $$-norm (but it can be $$ L_1 $$ norm too) regularization, where $$ \lambda $$ is the regularization strength.

```
Quick notes: The $$ L_2 $$​-norm regularization helps prevent weights from becoming too large, effectively controlling overfitting and ensuring weights stay closer to the origin. On the other hand, the $$ L1 $$​-norm encourages sparsity in the weights, driving many of them to zero.
```

Now the viewpoints as elucidated in the tweet are
- Optimization theory
- Bayesian theory 
- Empirical Risk learning theory (Statistical Learning Theory)

#### Optimization theory perspective

#### Bayesian theory perspective

#### Empirical Risk learning theory perspective

---
### References
- 
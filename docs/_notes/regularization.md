---
layout: default
title: Different view points of regularization
category: "In Too Deep (Learning)"
---
# How Regularization ?

![profileimg](/assets/is_regularisation.webp)

Date: 14/01/2025

I came across this [tweet](https://x.com/andrew_n_carr/status/1875625454025240730) (or should I call it an "X post" now?) and found it both interesting and personally alarming—mainly because I couldn’t immediately recall what the KKT conditions are off the top of my head. So, this post is meant to help me revisit and brush up on some basic concepts.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Here&#39;s a great ML interview question: <br><br>First ask about regularization. The candidate will likely talk about norm penalties on weights.<br><br>Then ask &quot;why do we do lambda norm penalties, - lambda|w| , instead of directly constraining |w|&lt;R if they&#39;re essentially equivalent under…</p>&mdash; Andrew Carr (e/🤸) (@andrew_n_carr) <a href="https://twitter.com/andrew_n_carr/status/1875625454025240730?ref_src=twsrc%5Etfw">January 4, 2025</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

#### Whazzat
First, let me rephrase the question for clarity and brevity. The focus is on the $\lambda$ parameter in the optimization framework:

$$
\min_{\theta} \mathcal{L}(\mathcal{D}; \theta) + \frac{\lambda}{2} \|\theta\|_2^2
$$

Here, $$ \mathcal{L}(\mathcal{D}; \theta) $$ denotes the primary loss function (e.g., cross-entropy or mean squared error),and $$ \mathcal{D} $$ represents the dataset used to train the model. The second term represents the $$ L_2 $$-norm (but it can be any $$ L_p $$ norm depending on your objective) regularization, where $$ \lambda $$ is the regularization strength.

**Quick notes**: The $$ L_2 $$​-norm regularization helps prevent weights from becoming too large, effectively controlling overfitting and ensuring weights stay closer to the origin. On the other hand, the $$ L1 $$​-norm encourages sparsity in the weights, driving many of them to zero.

Now the viewpoints as elucidated in the tweet are
- Optimization theory
- Bayesian theory 
- Empirical Risk learning theory (Statistical Learning Theory)

**NOTE:** Over the post, there will be some terms that I too am not super-familiar with but I hope to cover them as much as this post requisites


#### Optimization theory perspective

Directly constraining $$ \|\theta\|_2 \le C $$, (where C is some constant) leads to constrained optimization view point, which requisites methods like projection method or Lagrange multiplier method. Whoa... what is the projection method? Well, the projection method treats the objective (the thing you're optimizing) as if it were unconstrained and then finds the closest point in the valid space (the set of points that satisfy the constraints) to the solution. The Lagrange multiplier method, on the other hand, is a way to convert a constrained optimization problem into an unconstrained one. 

In general the difference is as follows:

| Feature               | Projection Method                        | Lagrangian Method                             |
|-----------------------|------------------------------------------|-----------------------------------------------|
| Approach              | Iterative projection onto the feasible set | Penalizes constraint violation using multipliers |
| Constraint Handling   | Direct, via projection                   | Indirect, via Lagrange multipliers            |
| Complexity            | Simple for convex constraints            | More complex, requires solving KKT conditions |
| Suitability           | Best for simple, convex constraints      | Best for complex or non-linear constraints    |
| Convergence           | May be slow if the projection is expensive | Convergence depends on proper multiplier updates |


We are more interested in langrage multiplier method. In general if there is an objective $$ \min f(x) $$ subject to constraints: $$ g(x) \leq 0 $$ and $$ h(x) = 0 $$. Then, Lagrangian is constructed as 

$$
\mathcal{L}(x,\mu, \lambda) = f(x) + \sum_{i} \lambda_i g_i(x) + \sum_{j} \mu_j h_j(x) 
$$

where $$ \lambda_i \geq 0 \forall i $$ are multipliers for inequality constraints and $$ \mu_j $$ are equality constraint multipliers. The reason for non-negativity of $$ \lambda_i $$ is given in this [answer](https://math.stackexchange.com/a/4499371/1323522). Once the lagrangian is formulated, the [KKT conditions](https://en.wikipedia.org/wiki/Karush%E2%80%93Kuhn%E2%80%93Tucker_conditions) are solved:
- $$ \nabla_x \mathcal{L}(x, \lambda, \mu) = 0 $$ : Gradient of the Lagrangian with respect to xx should be zero.
- $$ g_i(x) \leq 0, h_j(x) = 0 $$ : Constraints must be satisfied.
- $$ \lambda_i \geq 0 $$ : The Lagrange multipliers for inequality constraints must be non-negative.
- $$ \lambda_i g_i(x) = 0 $$: The complementary slackness condition, which ensures that if a constraint is violated, the corresponding multiplier is zero.

**Now to the actual answer**
- Non-convex Objective: While the $$ L_2 $$ norm constraint itself is convex, the objective in neural networks (such as the loss function) is non-convex. This means that even though the constraint is convex, the entire problem is non-convex, making methods like projection less effective.
- Computational Complexity: The projection method involves recalculating projections onto the constraint set (the $$ L_2 $$ ball) after every gradient update, which can be computationally expensive, especially for large networks with many parameters.
- Gradient Descent: In neural networks, we typically use gradient-based optimization methods like SGD or Adam. These methods work well with a loss function that is smooth and differentiable. Adding a projection step after every update interferes with the smooth nature of gradient descent and introduces extra computational overhead.

#### Bayesian theory perspective

From a Bayesian perspective, regularization can be understood as incorporating prior knowledge about the model parameters into the learning process. This connection arises naturally through the maximum a posteriori (MAP) estimation framework. 

**Stating the obvious**: The Bayes theorem states that $$ P(\theta  \vert \mathcal{D}) = \frac{P(\mathcal{D} \vert \theta )P(\theta)}{P(\mathcal{D})} $$, where
- $$ P(\theta  \vert \mathcal{D}) $$ is the posterior distribution of the parameters given the data.
- $$ P(\mathcal{D}  \vert \theta) $$ is the likelihood of the data given the parameters.
- $$ P(\theta) $$ is the prior distribution over the parameters
- $$ P(\mathcal{D}) $$ is called the evidence or the normalizing constant

** Danny *sighed* as he remembered his past Kafkaesque ordeal endured from the Bayesian bureaucrats for not stating the obvious.

In Bayesian learning, we seek the posterior distribution $$ P(\theta  \vert \mathcal{D}) $$, which balances the prior $$ P(\theta) $$ (what we believe about $$ \theta $$ before seeing data) and the likelihood $$ P(\mathcal{D}  \vert \theta) $$ (what the data tells us about $$ \theta $$). However, we are often concerned with the mode of posterior distribution,
$$
\begin{aligned}
\theta_{MAP} &= \text{argmax}_{\theta} P(\theta \mid \mathcal{D}) \\
&= \text{argmax}_{\theta} P(\mathcal{D} \mid \theta) P(\theta) \\
&= \text{argmin}_{\theta} \left[ -\log P(\mathcal{D} \mid \theta) - \log P(\theta) \right]
\end{aligned}
$$

Now, the term $$ -\log{P(\mathcal{D}  \vert \theta)} $$ corresponds to the loss function like MSE or cross entropy. The term $$ -\log{P(\theta)} $$ acts as regularizer that penalizes certain values of $$ \theta $$ depending on what our prior distribution is. If our prior is Gaussian $$ \mathcal{N}(o,\sigma^2) $$, then the $$ - \log{P(\theta)} \propto \frac{\|\theta\|^2}{2\sigma^2}$$ which is same as $$ \lambda \|\theta\|_2^2$$. If the prior were Laplacian $$ \mathcal{L}(0,b) $$, then $$ - \log{P(\theta)} \propto \frac{ \vert{\theta}\vert}{b}$$ which is same as $$ \lambda  \vert{\theta}\vert $$. 

Direct constraints like $$ \|\theta\|_2 \le C $$ in optimization can be seen as equivalent to assuming a uniform prior distribution over the feasible set of values. The constraint treats all values within the feasible region as equally likely, offering no additional information about the distribution of the parameters. On the other hand, a Gaussian prior with $$ \lambda = \frac{1}{2\sigma^2}$$ incorporates information about the distribution of the parameters by specifying a belief about their likely values (via the mean and variance of the distribution). This allows for probabilistic tuning of the model based on the chosen prior distribution.

#### Empirical Risk learning theory perspective

I am not too sure about the in-depth details about this viewpoint

Trade-off between complexity and fit: Regularization via norm penalties balances the trade-off between fitting the data (empirical risk) and controlling the model's complexity. The parameter $$ \lambda $$ directly tunes this trade-off.
Continuity and flexibility: The $$ \lambda $$-norm penalty allows for a smooth control of the effective regularization strength, whereas a hard constraint ($$ \|\theta\|_2 \le C $$) can introduce discontinuities or abrupt changes in the solution as the constraint boundary is reached.

---
### References
- 
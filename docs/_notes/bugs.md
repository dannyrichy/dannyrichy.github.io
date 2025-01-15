---
layout: default
title: Bugs in Danny's understanding
category: "BUGGGGGGGS 🐛"
---
## Where I was completely wrong in my understanding

Intended to remind myself to be humble when I think I am at the top of the world. 
** *Somewhere from the abyss of my youtube history, JK:* **WHO IS THE OBSERVER OBSERVING?** **

---
#### Gradient clipping
Remember when you thought gradient clipping worked like a g.i.f function? (Of course, I realize the "f" in g.i.f stands for "function.") You believed that when the norm of the gradient crosses a threshold, a constant gradient is applied to all the parameters. If you had taken the time to write down what you thought, you would have realized how nonsensical it was. If the gradient vector were $$ gradVector=C\mathbf{1} $$, tyou would essentially be subtracting a vector confined to either the positive or negative quadrant, serving god knows what purpose.

What is actually done, however, is to bound the gradient within a hypersphere whose radius equals the threshold. To achieve this, you scale the gradient vector by its norm and multiply it by the threshold. Thus,$$ g' =
\begin{cases} 
g & \text{if } \|g\| \leq T, \\
\frac{T}{\|g\|} g & \text{if } \|g\| > T,
\end{cases} $$.

However, I still haven't figured out if this is same as Adam optimizer, coz in Adam optimizer, you have adaptive learning rate for each parameter which is scaled by the moments of gradient. Though they are not entirely same, it feels like they both act using some sort of scaling mechanism.

---
#### Likelihood vs probability for continuous distribution
Okay, this is technically not a bug in my understanding, but it still deserves a place here because I did not fully grasp this concept. The PDF function returns the likelihood of a point, not the probability. You can find the probability of an event lying between two values by integrating the PDF between them.
---

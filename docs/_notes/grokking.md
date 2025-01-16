---
layout: default
title: Grokking
category: "In Too Deep (Learning)"
---

## Groking

Date: 15/01/2025

Briefly, this post is about grokking and how is prolly double descent or perhaps not. Most of the notes is borrowed from this [paper](https://openreview.net/forum?id=JqtHMZtqWm).

#### Elevator pitch version
Grokking (Nope it has nothing to do with X's grok) is the phenomenon where the validation accuracy increases much later in the training step as compared to train accuracy. Kinda sounds similar to double descent - where the test accuracy initially improves and then worsens (this is where practitioners initially said "A'ight man, this is where we stop") and then **MIRACULOUSLY** it increases again.

#### The Paper
The authors of the paper (henceforth mentioned as dem authors) piggy-back on the viewpoint that all that a neural network learns are just patterns - "pattern learning". With this viewpoint, the author puts forth two claims:
- Claim 1: *Grokking, like epoch-wise double descent, occurs when slow patterns generalize well and are ultimately favored by the training regime, but are preceded by faster patterns which generalize poorly.* **confused whaaat?**: Imagine an image of a "black dog" - there are various attributes in the image, but probably the easiest to learn is the color of the dog for which you can just build a model that aggregates the rgb value wise count. But there are also much more complex features (length between legs to length between tail and nose.... I'm just making it up but you get the point right?) that a simple model can't possibly learn. If I have hypothetically an infinite width neural network, then it should be able to learn all these patterns, the claim now is that this model will prioritize learning simpler features before learning complex features.
- Claim 2: *Patterns can be viewed as a function of model size as well as a function of training time, and learning dynamics are similar between these two cases.* Okay this is not super clear but I think they are trying to word whatever I said earlier better and precise.

.... TODO

---

### References
- [Unifying Grokking and Double Descent](https://openreview.net/forum?id=JqtHMZtqWm)
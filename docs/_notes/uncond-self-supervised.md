---
layout: default
title: Unconditional Self-supervised learning
category: "Biggus Papyrus"
---

# Unconditional Image generation

Date: 16/01/2025

Briefly, this post is about representation learning from this [paper](https://openreview.net/forum?id=JqtHMZtqWm). I was asked to read this document as part of interview process for a PhD application. 

**What is it about?**: Author argues that unconditional image generation is stagnant as compared to conditioned image generation. States that in conditioned generation, there is an additional semantic representation that is missing in unconditional generation. So the question is can we replace this semantic representation by another representation that can aid in image generation. Main algorithm is called **RCG**


## Brief overview:
Has three parts in RCG - SSL encoder, representation generator and image generator. 

#### SSL encoder
MoCo v3 encoder trained on ImageNet is used as an off-the-shelf image encoder. Regularizes the representations on a hyper-sphere; characterized by two properties - (i) it is simple enough to be modeled effectively by an unconditional representation generator (**WHAT THE HELL DO THEY MEAN?**) - define simple enough; (ii) it is rich in high-level semantic content which aids image generation - you know the main point.

#### Representation Generator
This title is weird. 


.... TODO

---

### References
- [Return of Unconditional Generation: A Self-supervised Representation Generation Method](https://openreview.net/pdf?id=clTa4JFBML)
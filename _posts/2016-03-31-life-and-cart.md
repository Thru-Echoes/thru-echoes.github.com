---
layout: post
title: "Evolution in a CART"
excerpt: "Initial thoughts on conceptualizing evolution through deicision trees"
tags: [evolution, mathematical model, simulation, cart, decision tree, theoretical evolution]
comments: true
image:
  feature: glitch-space/glitch-space-2.jpg
  credit:
  creditlink:
---

Lately, I have been playing around with ideas of linking predictive analysis and natural evolution (via natural selection) thinking. Namely, I have been thinking about conceptualizing evolution as a basic decision tree. Overview: I see links between how decision trees work and a trait frequency view of evolution.

## Some Definitions

* CART: classification and regression trees
* Trait: some phenotypic (but not necessarily phenotypic) attribute of a lineage
* Lineage: evolutionary history of a species
* Evolutionary History: species, its parent(s), its parent(s) parent(s), ..., ancestors
* Genes: some collection or single unit of genetic material for a trait(s)
* Loss / Gain Function: a change in some values (variance or fitness) in nodes in deicison tree

## The Key Analogy

The key in this analogy is the conceptualization of lineages, fitness, and frequencies within our evolutionary decision tree. Our data, instead of a finite dataset, is dynamic based on the current node. The node-specific data represents the frequencies of traits within some pool of interacting genetic material. This is a bit of a vague definition on purpose: a pool of interacting genetic material can be thought of as a population where genes are recombinatory or as some greater definition that includes other species and migration. Vague definitions sometimes allow a more generalizable concept to be used - I use this in my current definitions of pools of genetic material, traits, and significant trait frequencies.

Moving on: each node is a generation of some set of trait frequencies. For each node we want to split the data (trait frequencies) to create the set of trait frequencies for the next generation (next node). Splits occur based on optimizing a loss or gain function. In our case here, we are optimizing for fitness. Note: this model of selecting / optimizing on trait frequencies allows us to conceptualize evolution not at the species level. This implies that speciation events can occur as our trait frequency trees are generating. However, speciation events are not independent - they are products of these trait frequency lineages (branches of the decision tree). It is also important to note that these lineages of trait frequencies can end (i.e. go extinct). Extinctions at the trait frequency level could cause extinction at the species level, but this is not necessarily the case.

I have much more coming on this topic including visuals, plots, and more details. For now, I will end with a wrapping conceptual overview: the data at each node (each generation) is a set of trait frequencies that depends on the previous node (previous generation). Trait frequencies are selected on as optimization a loss or gain of fitness. Just like natural evolution and CART, there is no retroactive adjustments or modifications of any previous node's split / optimization. For example, each node will split towards hte most optimial outcome (either on data variance or trait frequency fitness). This happens only at the current node with a sort of assumption that the next node will have the same environment. Think about this point in this way: a species will pass on genes to the next generation that are selected for in the current generation's environment, rather than a prediction of what the next generation's environment will be. There are prediction of the future with evolution - neither with this concept of trait frequency lineages nor basic decision trees. In addition, there will not be suboptimal decision for the current node with the expectation (or predictive knowledge) that this will give the next generation a more optimal decision for the next generation after that. That would be So Raven.   

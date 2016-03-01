---
layout: post
title: "Learning to Conceptualize Models"
excerpt: "Intro to Creating Mathematical Models and Computer Simulations"
tags: [model thinking, mathematical model, simulation, dynamic systems, agent based, individual based]
comments: true
image:
  feature: glitch-space/glitch-space-1.jpg
  credit:
  creditlink:
---

Creating mathematical / statistical models and computer simulations requires a host of computer programming abilities. However, understanding how to conceptualize models and simulations is a necessary precursor and can be done irrespective of programming and even a computer. This repository will have some example systems (with a focus on ecological systems) that require models and simulations built for them. Anyone using this repository should go through the steps of model building for each example <strong>WITHOUT THE USE OF A COMPUTER!</strong>

I have a [repository on Github](https://github.com/Thru-Echoes/practice-models) that has this file. I plan to incorporate more examples and maybe show diagrams and final modeling results in <code>R</code>, <code>JS</code>, or maybe <code>Python</code>.

## Steps to Building a Model

Most of the steps involved with building a model do not require programming or a computer at all. In fact, modelers should always (with some exceptions here and there) do nearly all of the modeling without a computer. Programming and creating the computer simulation is almost always the last step in the process.

### Some Definitions

1. A model is a representation of reality.

2. system being modeled is that reality. So reality within a model is dependent on the model.

3. The system could be a population of land animals grazing in North America (e.g. cows eating grass). If that is our system (= reality) then we will probably not include fish in the Mediterranean Sea. The reality of this model does not include those fish. That is how the reality of each model may be different.

4. Also - this flows into the concepts of what to include in the model. If we are trying to model the amount of grass the population of cows eat over the course of 10 years we probably do not want to include each individual's body size, colors, distance between eyes, etc in the model. So that means that we may have a model of cows eating where the reality of that model does NOT include physiological properties of those cows...because we are not interested in that part of the cows!     

### An Example System

Here is an example of a system we may want to model. Below I will reference it to demonstrate how it could be modeled.

There is a population of fish <code>AAA</code> and another population of fish <code>BBB</code>. AAA are roughly 0.5-1m large with females usually on the upper end and males on the lower. BBB are roughly 1-2m large with no significant difference between females and males. Local fishermen populations would benefit from understanding the population dynamics between the two species of fish. It is known that BBB is a predator of AAA. The diet of BBB is usually between 50-80% AAA individuals. AAA only eats little cute water plants. It is speculated that the health of the ecosystem is dependent on the interactions of AAA and BBB. It is also known that the stability of population BBB depends on the population AAA (for food). Lastly, it is known that the population of AAA could explode if not eaten - which would result in all resources of the ecosystem depleting due to over-population. Make a model of this system.     

### Step 1: Conceptualize the System

The system is the natural / real thing you are trying to model.

* Goal: Deconstruct the system into all relevant components.

It looks like BBB is a predator of AAA, BBB requires AAA to survive, and the health of the ecosystem depends on a great model! The size of the fish may not be relevant. The breakdown of diets may not be important other than showing that BBB requires the consumption of AAA to survive.    

### Step 2: Conceptualize the Model

The model is a representation of the system. This step requires no code. This step could be verbal and linked with <code>Step 1.</code> A great thing to add here is an intial, simple flow diagram showing the input and output of each component of the system.

* Goal: Make a simple flow diagram of the system

Maybe we can assume there is enough food (plants) for AAA to survive. So AAA are just reproducing and maybe die at some small, natural rate. BBB require AAA to survive. BBB eat AAA.

Perhaps we could make two boxes. One would say AAA and have an arrow circling back to it that represents births. The AAA box would also have an arrow coming out of it (or negative arrow) that represents deaths by being eaten by BBB. Box BBB would have this arrow coming into it (BBB survives by eating AAA). Maybe both boxes have small negative arrows coming out of them - representing natural death rates. So what is this model then?  

### Step 3: Outline Model | Pseudo-math

* Goal: Create pseudo-math equations (maybe some pseudo-code?) that shows what this system is doing.

Perhaps the change of <code>AAA = birth_rate * (number_of_AAA) - kill_rate * (number_of_BBB)</code>

and...

<code>BBB = kill_rate * (number_of_AAA) - starve_rate * (number_of_BBB)</code>

and maybe that <code>starve_rate</code> represents density dependence. This could show that there is competition between BBB individuals.  

### Step 4: Detailed Flow Diagram

* Goal: Create a paper model that is a near complete model with detailed psuedo-code and pseudo-math.

Use the components from the <strong>Nova Modeling Software</strong> to create a detailed model on paper. In this section you can use visual concepts like <code>stock-and-flows</code>, <code>agents</code>, <code>terms</code>, <code>layers</code>, <code>CodeChips</code>, <code>agent-vectors</code>, <code>cell-matrix</code> etc.

Perhaps there is a term (i.e. single-value) that is <code>birth_rate</code>. An arrow could connect it to a flow called <code>nextAAA</code> that goes into a stock called <code>thisAAA</code>. You could draw a box to the side / below that shows the contents of <code>nextAAA</code>. Maybe it says the following:

```
    birth_rate * (thisAAA)
```     

The above would represent the accumulation of AAA. To show the eating process (subtraction) we could draw a flow out of the <code>thisAAA</code> stock that could be called <code>outAAA</code>. There could be an array coming in from the stock <code>thisBBB</code> that connects to <code>outAAA</code> flow. There could also be a <code>kill_rate</code> term connecting. Maybe the code inside this flow could say:

```
    kill_rate * (thisBBB)
```

### Step 5: Create Computer Model | Simulation

Now we create the computer code / model / simulation...

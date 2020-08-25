---
toc: true
layout: post
comments: true
title: Seldon Super Series
description: Table of Contents for series of posts
sticky_rank: 1
categories: [markdown, seldon, kubernetes, python] 
---
## Intro 
I work on a team building an ML platform to allow researchers to deploy, monitor, and iterate on production machine learning models. The platform leverages [seldon-core](https://docs.seldon.io/projects/seldon-core/en/v1.1.0/), an open source platform to deploy scalable machine learning models on kubernetes. 
Kubernetes is an intimidating subject. From the control-plane, to pods, to volumes, to everything else, there is always more you didn't even know you didn't know. My journey to getting familiar with kubernetes was learning through seldon-core. I had never used kubernetes before, but to leverage seldon, it is necessary. Over the past few months I've become comfortable developing, debugging, and deploying projects on a kubernetes cluster. 
Seldon-core is a great project to build kubernetes knowledge around. It leverages some advanced kubernetes concepts under the hood, while remaining easy to use and powerful. Not to mention, it is much easier to build motivation around a subject when you are actually building, instead of just reading the documentation. 

## Goals
I am not a kubernetes expert, but I have become comfortable enough to be highly productive working with kubernetes. This comfort level was developed through muscle memory using common kubectl commands, learning the basics of kubernetes built-in objects vs custom resources, finding errors, and more. With that in mind, here are my goals: 
* Main goal: Give readers a clear path to the "highly productive with kubernetes" level. 
* Stretch goal: Have readers match my comfort level in only one week. 
The Seldon Super Series is built around these goals. To do this, I wrote this series to lay out the resources I found my most useful along with some posts I wrote to show lessons I learned through trial and error.

#### Who's it for? 
This series is useful for anyone looking to build a deeper understanding of kubernetes. Seldon-core is just a great vehicle for this learning. If you are also interested in leveraging seldon, all the better!
You can be a complete kubernetes beginner, or come with some familiarity. If you are already familiar with kubernetes, feel free to jump to posts further into the series that get into more complex material! 
All of the examples throughout this tutorial are written in python. Most of the code examples are straightforward, with the focus on kubernetes and seldon, so even if you have a different preferred language, you should be able to following along just as well. 
This series is useful for 

#### How to get started
If you are completely new to kubernetes, there is no better place to start than the [kubernetes interactive tutorial](https://kubernetes.io/docs/tutorials/kubernetes-basics/create-cluster/cluster-interactive/). I suggest following this tutorial all the way through before getting started on anything else. It requires no install, no setup, and introduces fundamentals used when working with any app deployed on a cluster. 
After that, I suggest following [Launch a local kubernetes cluster](https://ntorba.github.io/writing/jupyter/2020/07/17/local-kubernetes.html) to get a kubernetes cluster running on your local machine with [kind](https://kubernetes.io/docs/setup/learning-environment/kind/). If that doesn't work for you, there are many good resources available to get a cluster running on AWS or Google Cloud. Having a cluster to hack on is super imporant. You will not be able to build muscle memory without actually writing commands and debugging issues on your own setup. 
Once you have a cluster to hack on, get started with [First Seldon Deployment](https://ntorba.github.io/writing/kubernetes/docker/2020/07/30/first-seldon-deployment.html). Even if you have previous seldon experience, I suggest starting, here, because many other posts will use this as a baseline to build on (don't worry if you don't start here, though, any post that does require some setup will make that clear).

1. [Launch a local kubernetes cluster](https://ntorba.github.io/writing/jupyter/2020/07/17/local-kubernetes.html) 
    * Get a local kubernetes cluster up and running so you can experiment locally! Important for those of us who don't have easy access to a remote cluster.
2. [First Seldon Deployment](https://ntorba.github.io/writing/kubernetes/docker/2020/07/30/first-seldon-deployment.html)
    * Deploy a model endpoint on kubernetes!
3. [Multi-component Seldon Deployment]()
    * Use multiple seldon-core components to deploy and inference graph!
4. [Explore the Kubernetes API]()
    * Use `kubectl proxy` to understand how to communicate with a kubernetes cluster!
5. [Seldon-core Custom Resource and Operator](). Create your first seldon deployment and read about what makes the seldon deployment custom resource so useful. 
    * Take a closer look at how seldon-core and seldon-core-operator extend the kubernetes api and make it easy to deploy seldon inference graphs! 
6. [Debugging Seldon Deployments](). Take a look at where to find your logs and diagnosis some common issues. 
7. [Seldon-core analytics and load testing with Locust]()
8. [Multi-pod Seldon Deployments](). 
    * Deploy individual components of your inference graph in their own pods to define custom deployment specs! 
9. [Horizontal Pod Autoscaling Seldon Deployments]()
    * Autoscaling your deployments! 
10.  [CD with Argocd]() 
    * Try out Argocd for continuous deployment!
    

# Why Seldon-core? 
Seldon-core is an open source projects built by the London based startup [Seldon](https://www.seldon.io/). With seldon-core, you can use python (and java) to easily deploy ML models built in any framework at scale. However, they offer tools for more than just model serving. With seldon-core, you construct an inference graph. The inference graph is built with [these components](https://docs.seldon.io/projects/seldon-core/en/v1.1.0/python/python_component.html): 
* Model
* Transformer
* Combiner 
* Router
These additional components add the ability to create much more than just a single model. You can set up custom A/B tests, multi-armed bandits, scalable ensemble systems, and much more. In short, seldon-core inference graphs are powerful! 

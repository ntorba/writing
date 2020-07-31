---
toc: true
layout: post
comments: true
title: Learning Kubernetes Through Seldon
description: Table of Contents for series of posts
sticky_rank: 1
categories: [markdown, seldon, kubernetes, python] 
---
# Intro 
I recently started working with with the [seldon-core](https://docs.seldon.io/projects/seldon-core/en/v1.1.0/) project. I am working on a team now that is developing an ML platform to allower researchers to quickly serve and monitor ML models at scale. Seldon-core is a fantastic tool to build on top of for this project. Seldon-core deploys models at scale by leveraging kubernetes. The only problem was, I had never used kubernetes before. 

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
These additional components add the ability to create much more than just a single model. You can set up custom A/B tests, or 1-armed bandit systems with the router, combine results from two different models with the combiner, and have independent components (which allows separate scale settings) to transform the input data. Seldon-core inference graphs are powerful! 

# What's this series? 
In order to take advantage of seldon-core, you need to become familiar with some basic kubernetes fundamentals, so that's what I did. First, I followed the [kubernetes interactive tutorial](https://kubernetes.io/docs/tutorials/kubernetes-basics/create-cluster/cluster-interactive/) to get a handle. Then, I dove right into seldon deployments. Working with seldon-core and building implementations of projects is a great way to get the kubernetes basics down. At the start, I couldn't tell you the difference between a kubernetes deployment and a service. Although I'm not an expert now, I'm comfortable with seldon deployments, all the components they run on top of, and how to quickly debug my implementations by checking through the logs of containers scattered throughout the different components of my seldon deployments. 
In this post, I link to, in order, posts I've written detailing the concepts and tools I learned to become confident in building and deploying at scale with seldon-core.

    
    

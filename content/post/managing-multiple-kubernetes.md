+++
author = "Arran Short"
date = 2020-01-21T11:33:12Z
description = ""
draft = false
slug = "managing-multiple-kubernetes"
title = "Managing Multiple Kubernetes Clusters easily with konfig and kubectx"

+++


At work I've been setting up a few Kubernetes clusters for AWX, Vault and other fancy tools.

Getting helm and the like working with k3s and managing it all nicely with kubectl has been a bit of a faff to say the least.

I've looked at kubectl context before but it hadn't sunk in how to manage it all.

In comes konfig and kubectx:

Konfig

This can be installed via krew ( a kubectl plugin manager ) and the awesome piece of software allows you to easily manage your .kube/config file by importing new k8s configs, e.g.

`kubectl konfig import --save your-new-k8s-config.yml`

And that's it!

Now that you've got a kubectl config with loads of clusters what do you do? install kubectx of course!



Kubectx

This is a very simple plugin to allow easy viewing of your clusters and to then switch to them e.g.

`kubectx name-of-your-cluster-context`

Now you can relax and enjoy managing multiple clusters from one kubectl window.








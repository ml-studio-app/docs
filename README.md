---
description: Freeing Data Scientists to focus on hard and creative ML tasks
---

# ML Studio

![New deployment demo](.gitbook/assets/flow-deploy.gif)

## Key features

* **Try your changes** before committing to anything.
* **Open:** your deployment specs and models are stored in open format.
* **Reproducibility**: reproducing previous results easily. 
* **Auto Deployments:** deploy your models in minutes.
* **Autoscaling:** automatically scales APIs to handle production workloads.
* **Zero DevOps**: focus on what matters, you w'not have to worry about devops.
* **CPU / GPU instances:** ML Studio just works on your infrastructure.
* **Preemptible \(Spot\) instances:** use preemptible VMs for cost savings.

## What is ML Studio?

Build, deploy and manage your ML models using one service**.**

**ML Studio** is a cloud-native app build on-top of Kubernetes. It is cloud-agnostic and can be deployed on its own or to existing clusters. 

**ML Studio** is built around a few open-source tools your already use and other tools we build ourselves to make your life easier: 

* **GIT**: track your work and deployments configuration
* **Docker**: build your deployment images and deploy your work inside your k8s cluster
* **Voyager**: a simple but handy lightweight data visualization tool
* **Conda**: manage your Python environments
* **Jupyter**: our online IDE of choice
* **Boiler**: a tool we built to help you manage all your deployments

None of the tools we built are designed to lock you in.

## How it works?

If you are already using Git then you are going to fit right in because every change is tracked in Git automatically. Individual deployment configuration are tracked inside your Git repo under `.mlstudio/app.db`, it is SQLite database. And artifacts are stored in `/home/mlstudio/models` directory so together with the related deployment configuration you can reproduce the same results and review the code that lead to them. 

All that is open because we do not want to lock you in, we believe that after you try ML Studio you will be hooked. And if you ever feel want to leave you know that all your work and deployments configuration are yours and that you will be taking them with you.




---
description: Free Data Scientists to focus on hard and creative ML tasks
---

# ML Studio

![New deployment demo](.gitbook/assets/flow-deploy.gif)

## Key features

* **Try locally** before commiting to anything.
* **Open:** your deployment specs and models are stored in open format.
* **Reproducibility**: reproducing previous results easily. 
* **Auto Deployments:** deploy your models in minutes.
* **Autoscaling:** automatically scales APIs to handle production workloads.
* **Zero DevOps**: focus on what matters, you w'not have to worry about devops.
* **CPU / GPU instances:** ML Studio just works on your infrastructure.
* **Preemptible \(Spot\) instances:** use preemptible VMs for cost savings.

## What is ML Studio?

**ML Studio** is a cloud-native app build on-top of Kubernetes. This means it is cloud-agnostic and can be deployed on its own or to existing clusters. 

**ML Studio** has intuitive UI and is bundled with many open-source tools Data Scientists and Engineers already use daily. No lock-in tools, we simply want to free you to do your best work without having to worry about the mundane tasks.

## How it works?

If you are already using Git then you are going to fit right in because every change is tracked in Git automatically. Individual deployment configuration are tracked inside your Git repo under `.mlstudio/app.db`, it is SQLite database. And artifacts are stored in `/home/mlstudio/models` directory so together with the related deployment configuration you can reproduce the same results and review the code that lead to them. 

All that is open because we do not want to lock you in, we believe that after you try ML Studio you will be hooked. And if you ever feel want to leave you know that all your work and deployments configuration are yours and that you will be taking them with you.

## Roadmap

* **Testing**: add A/B, canaray and shadow testing support.
* **1-click app installs**: apps like AirFlow, Meltano, Seldon, ...
* **Drift alerts**: data drift detection alerts.
* **Pipelines:** simple pipelines tools
* HTTPS deployments out of the box.
* Better user calibration.
* Experiments tracking.
* Multiplce workspaces.
* [Request a feature](http://bit.ly/ml-studio-feature-suggestions).


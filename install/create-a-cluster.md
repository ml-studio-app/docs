---
description: Skip this step if you already have a cluster
---

# Create a cluster

Spinning up a cluster in easy, whether you want to try ML Studio locally or use it in the cloud.

## Cloud

#### Create a GKE k8s cluster

You need to have Google Cloud SDK for this step, follow the [instructions to install it here](https://cloud.google.com/sdk/docs/downloads-interactive#mac).

```bash
export cluster_name=mlstudio-cluster
export cluster_zone=us-central1-a

gcloud container clusters create $cluster_name \
    --machine-type=n1-standard-4 \
    --num-nodes 1 \
    --enable-autoscaling --min-nodes 0 --max-nodes 6 \
    --zone $cluster_zone
```

For cost savings you can also append `--preemptible` to the previous command. They offer the same machine types and options as regular compute instances and last for up to 24 hours.

You can also create a GPU accelerated cluster by appending `--accelerator type=nvidia-tesla-t4,count=1` to the previous command. And then creating a `DaemonSet` to instal Nvidia drivers.

```bash
kubectl apply -f https://raw.githubusercontent.com/GoogleCloudPlatform/container-engine-accelerators/master/nvidia-driver-installer/cos/daemonset-preloaded.yaml
```

So the final commands to create a preemptible GPU accelerated cluster would look like:

```bash
export cluster_name=mlstudio-cluster
export cluster_zone=us-central1-a

gcloud container clusters create $cluster_name \
     --machine-type=n1-standard-4 \
     --accelerator type=nvidia-tesla-t4,count=1 \
     --num-nodes 1 \
     --enable-autoscaling --min-nodes 0 --max-nodes 6 \
     --zone $cluster_zone
     --preemptible

# Install NVIDIA GPU device drivers
kubectl apply -f https://raw.githubusercontent.com/GoogleCloudPlatform/container-engine-accelerators/master/nvidia-driver-installer/cos/daemonset-preloaded.yaml
```

## Local

#### Create a [Minikube](https://minikube.sigs.k8s.io) k8s cluster

```bash
minikube start --cpus 5 --memory 10096
```

#### Docker Desktop

Download [Docker Desktop](https://www.docker.com/products/docker-desktop) application and follow the instructions on enabling Kuberentes.

You need a minimum of:

* 5 CPUs
* 8 Gb of RAM
* 15 Gb of fee desk space


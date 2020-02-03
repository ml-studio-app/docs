---
description: Skip this step if you already have a cluster
---

# Create a cluster



```text
#### Minikube
https://minikube.sigs.k8s.io
```shell script
# Create or start existing cluster
minikube start --cpus 5 --memory 10096

# Stop
minikube stop

# Delete
minikube delete
```

#### Docker Desktop
https://www.docker.com/products/docker-desktop

### Cloud
#### GKE cluster
```shell script
export cluster_name=mlstudio-cluster
export cluster_zone=us-central1-a

gcloud container clusters create $cluster_name \
    --machine-type=n1-standard-4 \
    --num-nodes 1 \
    --enable-autoscaling --min-nodes 0 --max-nodes 6 \
    --zone $cluster_zone
# TODO :: Save costs by using preemptible VMs. They offer the same machine types and options as regular compute instances and last for up to 24 hours 
#    --preemptible

# You can also create a gpu accelerated cluster or use your existing gpu accelretaed cluster
gcloud container clusters create $cluster_name \
#     --machine-type=n1-standard-4 \
#     --accelerator type=nvidia-tesla-t4,count=1 \
#     --num-nodes 1 \
#     --enable-autoscaling --min-nodes 0 --max-nodes 6 \
#     --zone $cluster_zone
# #    --preemptible

# # Install NVIDIA GPU device drivers
# kubectl apply -f https://raw.githubusercontent.com/GoogleCloudPlatform/container-engine-accelerators/master/nvidia-driver-installer/cos/daemonset-preloaded.yaml

# Set kubectl locally
gcloud container clusters get-credentials $cluster_name --zone $cluster_zone
```
```


# Cleanup

{% hint style="warning" %}
Make sure that all your changes are stored in remote Git repo and that you moved your artificats to permenant storage before going through these steps.
{% endhint %}

## Delete ML Studio release

```bash
helm del --purge mlstudio
```

## Cloud

#### GKE

```bash
gcloud container clusters delete $cluster_name --zone $cluster_zone
```

## Local

#### Minikube

```bash
minikube delete
```


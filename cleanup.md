# Cleanup



```text
```shell script
# Delete ML Studio release
helm del --purge mlstudio

# Delete the GKE cluster
gcloud container clusters delete $cluster_name --zone $cluster_zone
```
```


# Istio

### Download Istio

```text
curl -L https://git.io/getLatestIstio | sh -

cd istio-*/
```

### Install the istio-init chart to bootstrap all the Istio’s CRDs

```text
helm install install/kubernetes/helm/istio-init --name istio-init --namespace istio-system

# Wait for all Istio CRDs to be created:
kubectl -n istio-system wait --for=condition=complete job --all
```

### Install Istio

```text
helm install install/kubernetes/helm/istio --name istio --namespace istio-system
```

### Allow automatic Istio sidecar injector 

Allow sidecar injector on all containers in default namespace.

```text
kubectl label namespace default istio-injection=enabled

# Verify auto injection worked
kubectl get namespace -L istio-injection
```

### Cleanup

```text
# Back
cd ../

# Remove istio directory
rm -R istio-*/
```




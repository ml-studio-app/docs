# Istio

### Download Istio

```bash
git clone --depth 1 -b 1.4.0 https://github.com/istio/istio

cd istio
```

### Install the istio-init chart to bootstrap all the Istio’s CRDs

```bash
helm install install/kubernetes/helm/istio-init --name istio-init --namespace istio-system

# Wait for all Istio CRDs to be created:
kubectl -n istio-system wait --for=condition=complete job --all
```

### Install Istio

```bash
helm install install/kubernetes/helm/istio --name istio --namespace istio-system
```

### Allow automatic Istio sidecar injector 

Allow sidecar injector on all containers in default namespace.

```bash
kubectl label namespace default istio-injection=enabled

# Verify auto injection worked
kubectl get namespace -L istio-injection
```

### Remove temporary Istio files

```bash
# Back
cd ../

# Remove istio directory
rm -R istio-*/
```




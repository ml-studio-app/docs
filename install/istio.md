# Istio



```text
```shell script
curl -L https://git.io/getLatestIstio | sh -

cd istio-*/

# Install the istio-init chart to bootstrap all the Istio’s CRDs:
helm install install/kubernetes/helm/istio-init --name istio-init --namespace istio-system

# Wait for all Istio CRDs to be created:
kubectl -n istio-system wait --for=condition=complete job --all
```

```shell script
# Select a configuration profile and then install the istio chart corresponding to your chosen profile. The default profile is recommended for production deployments
helm install install/kubernetes/helm/istio --name istio --namespace istio-system

# Allow automatic Istio sidecar injector on all containers in default namespace
kubectl label namespace default istio-injection=enabled

# Verify auto injection worked
kubectl get namespace -L istio-injection

# Back
cd ../

# Remove istio directory
rm -R istio-*/
```
```


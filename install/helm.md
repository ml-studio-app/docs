---
description: ML Studio has not been with HELM 3.x yet
---

# HELM

### Install HELM 2.x

You will need `kubectl` to be able to finish this step, follow the [instructions to install it here](https://kubernetes.io/docs/tasks/tools/install-kubectl).

{% hint style="info" %}
Change `HELM_OS` to match your running OS before running the following commands
{% endhint %}

```bash
export HELM_VERSION=v2.16.0
export HELM_OS=darwin # windows # linux
wget -q https://get.helm.sh/helm-${HELM_VERSION}-${HELM_OS}-amd64.tar.gz -O - | tar -xzO ${HELM_OS}-amd64/helm > /usr/local/bin/helm && \
chmod +x /usr/local/bin/helm
```

### Setup Tiller Service account

```bash
cat <<EOF | kubectl apply -f -
apiVersion: v1
kind: ServiceAccount
metadata:
  name: tiller
  namespace: kube-system
---
apiVersion: rbac.authorization.k8s.io/v1beta1
kind: ClusterRoleBinding
metadata:
  name: tiller
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: cluster-admin
subjects:
  - kind: ServiceAccount
    name: tiller
    namespace: kube-system
EOF

helm init --service-account=tiller
helm repo update
```

### Ensure that tiller is secure from access inside the cluster

```bash
kubectl patch deployment tiller-deploy --namespace=kube-system --type=json --patch='[{"op": "add", "path": "/spec/template/spec/containers/0/command", "value": ["/tiller", "--listen=localhost:44134"]}]'
```

### Verify helm and tiller were installed properly

We can do so by checking the client and server versions.

```bash
helm version --short
```

{% hint style="info" %}
Wait for tiller to get ready.

You will know that it is ready when the previous command returns both the client and server versions.
{% endhint %}




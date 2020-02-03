---
description: ML Studio has not been with HELM 3.x yet
---

# HELM



```text
```shell script
# TODO :: Install helm 2.x if not installed, https://helm.sh/docs/install/#installing-helm
export HELM_VERSION=v2.16.0 # v3.0.2
export HELM_OS=darwin # windows # linux
wget -q https://get.helm.sh/helm-${HELM_VERSION}-${HELM_OS}-amd64.tar.gz -O - | tar -xzO ${HELM_OS}-amd64/helm > /usr/local/bin/helm && \
chmod +x /usr/local/bin/helm

# Setup Tiller Service account
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

# Ensure that tiller is secure from access inside the cluster
kubectl patch deployment tiller-deploy --namespace=kube-system --type=json --patch='[{"op": "add", "path": "/spec/template/spec/containers/0/command", "value": ["/tiller", "--listen=localhost:44134"]}]'

# Verify helm and tiller were installed properly, by checking the client and server versions
helm version --short

# TODO :: Wait for teller to get ready.
```
```


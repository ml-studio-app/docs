# Troubleshooting

## Check the backend logs

Access the backend logs for some details

```bash
# Get the backend pod name
backend_pod_name=$(kubectl get pods | grep 'mlstudio-backend-deployment' | awk '{print $1}' | head -n 1)

# Check the logs
kubectl logs $backend_pod_name -c mlstudio-backend
```

## Install [k9s](https://github.com/derailed/k9s) to get an overview of your setup

```bash
brew install derailed/k9s/k9s

k9s
```


# Troubleshooting

## Check the backend logs

Access the backend logs for some details

```bash
# Get the backend pod name
kubectl get pods | grep 'mlstudio-backend-deployment' | awk '{print $1}' | head -n 1

# Check the logs
kubectl logs BACKEND_POD_NAME -c mlstudio-backend
```

## Install [k9s](https://github.com/derailed/k9s) to get an overview of your setup status

```bash
brew install derailed/k9s/k9s

k9s
```


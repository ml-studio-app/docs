# ML Studio

### Add ML Studio helm repo

```bash
helm repo add mlstudio https://ml-studio-app.github.io/helm-chart/
helm repo update
```

### Install ML Studio

```bash
helm install mlstudio/mlstudio
```



To install ML Studio **locally** you need to set this flag `installLocally`.

```bash
helm install mlstudio/mlstudio --set installLocally=true
```


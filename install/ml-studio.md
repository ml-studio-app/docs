# ML Studio

### Ad

### Ad

### Add ML Studio helm repo

```text
helm repo add mlstudio https://ml-studio-app.github.io/helm-chart/
helm repo update
```

### Install ML Studio

```text
helm install mlstudio/mlstudio
```



To install ML Studio **locally** you need to set this flag `installLocally`.

```text
helm install mlstudio/mlstudio --set installLocally=true
```


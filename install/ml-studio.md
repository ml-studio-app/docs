# ML Studio

### Add ML Studio helm repo

```bash
helm repo add mlstudio https://ml-studio-app.github.io/helm-chart/
helm repo update
```

### Install ML Studio

To install ML Studio **locally** you need to set this flag `installLocally`.

{% tabs %}
{% tab title="Cloud" %}
```bash
helm install mlstudio/mlstudio --name mlstudio
```
{% endtab %}

{% tab title="Local" %}
```
helm install mlstudio/mlstudio --name mlstudio --set installLocally=true
```
{% endtab %}
{% endtabs %}




# Usage

Once you have ML Studio installed, find out its the IP address to access it, login and start building.

### Find the IP to access ML Studio

```bash
kubectl get svc istio-ingressgateway -n istio-system
```

### Log in as an admin user

```yaml
  USER: admin
  PASSWORD: password
```

### Work directory

{% hint style="info" %}
ML Studio root work directory can be access at `/home/jovyan/work` inside jupyter pods and `/home/work` inside other pods.

All files you would like persisted should live under this directory.
{% endhint %}


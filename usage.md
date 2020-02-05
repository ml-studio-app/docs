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

**All files you would like persisted should live under this directory.**
{% endhint %}

## How to manage your python environment 

We recommend using `conda` to manage all your conda environment but you are free to use others.

{% hint style="warning" %}
**`base` conda environment will not get persisted**
{% endhint %}

#### **Create a new environment** 

Start a new terminal session under `Notebooks`

```bash
conda create --name py3 python=3.7 -y
```

#### Add it as a new Jupyter kernel

Before you can use this new python enviorment in your notebooks, you need to make Jupyter aware of it first.

```bash
conda activate test                   

ipython kernel install --user --name=py3
```

Finally, **refresh ML Studio web app** for your changes to take effect.


# Before

```
minikube  -p argodemo status
```

```
minikube  -p argodemo addons enable ingress
```

```
minikube  -p argodemo ip
```
> 172.17.0.2

Add an ingress path for argocd to the hosts file 
```
sudo vim /etc/hosts
```

> 172.17.0.2        argocd.argodemo.io

```
kubectl apply -f manafests/argocd/namespace.yaml
kubectl apply -n argocd -f manafests/argocd/install.yml
kubectl apply -n argocd -f manafests/argocd/ingress.yml
```

The default password is the name of the server pod

```
kubectl get pods -n argocd
```
> argocd-server-78ffb87fd8-tb9z9

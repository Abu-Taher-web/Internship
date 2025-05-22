### Download minikube

[Learning Source Link](https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fdebian+package#LoadBalancer)

```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube_latest_amd64.deb
```
### Run the debian file
```bash
sudo dpkg -i minikube_latest_amd64.deb
```

### Check if it is installed 
```bash
minikube version
```

### If you want, you can delete the debian file
```bash
rm minikube_latest_amd64.deb
```

### Inspect the available commands
```bash
minikube
#or
minikube --help
```

### Start the culster
```bash
minikube start
```

### Pause and unpause the cluster
```bash
minikube pause
#and
minikube unpause
```

### Stop the cluster
```bash
minikube stop
```

### Inspect whether the cluster is running or not
```bash
minikube status
```

### Minikube pods
```bash
kubectl get po -A
```

### Minikube dashboard
```bash
minikube dashboard
```

### Service

```bash
kubectl create deployment hello-minikube --image=kicbase/echo-server:1.0
kubectl expose deployment hello-minikube --type=NodePort --port=8080
```

```bash
kubectl get services hello-minikube
```


```bash
minikube service hello-minikube
```


```bash
kubectl port-forward service/hello-minikube 7080:8080
```

### Utility
```bash
minikube config set memory 9001
```


```bash
minikube addons list
```


```bash
minikube start -p aged --kubernetes-version=v1.16.1
```


```bash
minikube delete --all
```

```bash

```

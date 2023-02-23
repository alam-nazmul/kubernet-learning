### To install the latest minikube stable release on x86-64 Linux using RPM package:
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-latest.x86_64.rpm

sudo rpm -Uvh minikube-latest.x86_64.rpm
```

### From a terminal with administrator access (but not logged in as root), run:
```
minikube start
```

### minikube can download the appropriate version of kubectl and you should be able to use it like this:
```
minikube kubectl -- get po -A
```

### You can also make your life easier by adding the following to your shell config:
```
alias kubectl="minikube kubectl --"
```

### Initially, some services such as the storage-provisioner, may not yet be in a Running state. This is a normal condition during cluster bring-up, and will resolve itself momentarily. For additional insight into your cluster state, minikube bundles the Kubernetes Dashboard, allowing you to get easily acclimated to your new environment:
```
minikube dashboard
```

### Pause Kubernetes without impacting deployed applications:
```
minikube pause
```

### Unpause a paused instance:
```
minikube unpause
```

### Halt the cluster:
```
minikube stop
```

### Delete all of the minikube clusters:
```
minikube delete --all
```
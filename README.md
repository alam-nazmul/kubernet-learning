# kubernet-learning
_This is a kubernet journey from scratch_


### Create a pod with images
```
kubectl run nginx --image=nginx
```

### Show pods
```
kubectl get pods -o wide
```

### Show details of a pod
```
kubectl describe pod nginx
```

### Delete the created Pods
```
kubectl delete pod nginx
```

### Remember !!!!
_When kind = POD and Service the Version will be v1 and When kind = Replicaset and Deployment the Service will be apps/v1_

### Create a replication controller from a YAML file
```
kubectl create -f replica-controller.yaml
```

### Show the replication controllers
```
kubectl get replicationcontroller
```

### Delete the replicationcontroller
```
kubectl delete replicationcontroller myapp-rc
```

### Create a replica-set from a YAML file
```
kubectl create -f replica-set.yaml
```

### Show the replica-set
```
kubectl get replicaset -o wide
```

### Delete the replica-set
```
kubectl delete kubectl delete  replicaset myapp-replicaset
```

### Scaling replica-set by YMAL file
Edit the YAML file with replicas number then put
```
kubectl replace -f replica-set.yaml
```
or
```
kubectl scale --replicas=3 -f replica-set.yaml
```
or
```
kubectl scale --replicas=3 replicaset myapp-replicaset
```

### For details of running Replicaset
```
kubectl describe replicaset myapp-replicaset
``` 

### For edit of running Replicalist
```
kubectl edit replicaset myapp-replicaset
```
We can change the number of replicas by editing on "replicas" section

## The labels of "matchLabels" and "POD" will be same. No matter what is about the label of ReplicaSet

### Show all the created objects at once
```
kubectl get all
```

### Deployment create help command
```
kubectl create deployment --help
```

### Rollout status
```
kubectl rollout status deployment/myapp-deployment
```

### Check Rollout history
```
kubectl rollout history deployment/myapp-deployment
```
or
```
kubectl rollout history deployment myapp-deployment
```

### For recoard the deployment logs
```
kubectl create -f deployment/deployment.yaml --record
```

### For rollback the current deployment version to previous one
```
kubectl rollout undo deployment myapp-deployment
```

### Types of Kubernet services
    -   NodePort
    -   ClusterIP
    -   LoadBalancer


### Nodeport default range
    -   From 30000 to 32767

### Remember !!! 
_When you declare a SERVICE the specification > selector parameters will be same as DEPLOYMENT's template > metadata > labels_


### Create a service by YAML file
```
kubectl create -f service/service-defination.yaml 
```

### Check the running services
```
kubectl get service -o wide
```

### Check the service url
```
minikube service myapp-prod-deploy --url
```

### Check the nodes detail
```
kubectl get nodes
```


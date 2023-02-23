# kubernet-learning
This is a kubernet journey from scratch



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
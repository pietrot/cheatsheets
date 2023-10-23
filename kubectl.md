# kubectl
## Commands
### Get deployments
`kubectl get deployments -n {environment}`

### Restart a deployment
kubectl rollout restart deployment {deploymentName} -n {environment}

### rollback a deployment
kubectl rollout undo deployment/{deploymentName} --to-revision={revisionID} -n {environment}

### Get stored secret
`kubectl get secret {secret-name} -n {environment} -o yaml`

### Create secret
`kubectl create secret generic {secret-name} --from-literal={key}={value} -n {environment}`

### Edit secret
`kubectl edit secret {secret-name} -n {environment}`

### Delete secret
`kubectl delete secret {secret-name} -n {environment}`

### Port forwarding
`kubectl port-forward {pod-name} 8080:8080 -n {environment}`

### Get pods
`kubectl get pods -n {environment}`

### Describe a pod
`kubectl describe pod {pod-name} -n {environment}`

### Get managed certificates
`kubectl get managedcertificates -n {environment}`

### SSH into pod
`kubectl exec -it -n production {pod-name} -- /bin/bash`

### Tail logs for a given pod
`kubectl logs --follow {pod-name} -n {environment}`

# Base64 encode/decode values
```
echo -n {secret_value} | base64
echo {secret_value} | base64 -d
```

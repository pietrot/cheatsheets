# kubectl
## Notes
> Note: The kubectl get command features a rich set of flags that allows you to customize the output format using the `-o` or `--output` flag, for example. You can specify the `-w` or `--watch` flag to start watching updates to a particular object.—https://kubernetes.io/docs/reference/kubectl/#examples-common-operations

## Config
### View your current context
```
$ kubectl config current-context
```

### List and switch contexts
```
$ kubectl config get-contexts
$ kubectl config use-context {context-name}
```

## Commands
### Get deployments
```
$ kubectl get deployments -n {environment}
```

### Restart a deployment
```
$ kubectl rollout restart deployment {deploymentName} -n {environment}
```

### rollback a deployment
```
$ kubectl rollout undo deployment/{deploymentName} --to-revision={revisionID} -n {environment}
```

### Get stored secret
```
$ kubectl get secret {secret-name} -n {environment} -o yaml
```

### Create secret
```
$ kubectl create secret generic {secret-name} --from-literal={key}={value} -n {environment}
```
-or from file-
```
$ kubectl create secret generic {secret-name} --from-file=/path/to/file -n {environment}
```

### Edit secret
```
$ kubectl edit secret {secret-name} -n {environment}
```

### Delete secret
```
$ kubectl delete secret {secret-name} -n {environment}
```

### Port forwarding
```
$ kubectl port-forward {pod-name} 8080:8080 -n {environment}
```

### Get pods
```
$ kubectl get pods -n {environment} -w
```

### Describe a pod
```
$ kubectl describe pod {pod-name} -n {environment}
```

### Get managed certificates
```
$ kubectl get managedcertificates -n {environment}
```

### SSH into pod
```
$ kubectl exec -it -n production {pod-name} -- /bin/bash
```

### Tail logs for a given pod
```
$ kubectl logs --follow {pod-name} -n {environment} -c {container-name}
```

# Base64 encode/decode values
```
$ echo -n {secret_value} | base64
$ echo {secret_value} | base64 -d
```

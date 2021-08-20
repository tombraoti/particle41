### 1. Deploy a sample Linux workload

```sh
kubectl create namespace <my-namespace>
```
Then create a sample deployment file - sample-service.yaml and apply the deployment -
```
	kubectl apply -f sample-service.yaml
```

### 2. View all resources that exist in the my-namespace namespace.

```sh
kubectl get all -n my-namespace
```

### 3. View the details of the deployed service
```sh
kubectl -n <my-namespace> describe service <my-service>
```

### 4. View the details of one of the pods that was deployed

```sh
kubectl -n <my-namespace> describe pod <my-deployment-776d8f8fd8-78w66>
```

### 5. Execute a shell on one of the pods by replacing the <value> below with a value returned for one of your pods
```sh
kubectl exec -it <my-deployment-776d8f8fd8-78w66> -n <my-namespace> -- /bin/bash
```

### 6. Remove the sample service, deployment, pods, and namespace
```sh
kubectl delete namespace <my-namespace>
```

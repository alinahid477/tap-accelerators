
### in build cluster


```
kubectl apply -f build/workload.yaml
```

The above command will create:
- a workload to connect to supplychain (CI pipeline)
- a secret called src-git-secret (refered in workload.yaml) for the supplychain to pull application source code.

To see the logs for supplychain execution run the below command:

```
tanzu apps workload tail RPLC_WORKLOAD_NAME --since 1h -n RPLC_NAMESPACE_NAME
```

### in run cluster

```
kubectl apply -f run/deliverable.yaml
```
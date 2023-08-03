# Tanzu Application Platform

## Working on your WORKLOAD_NAME project

### Deploying to Kubernetes as a TAP workload with Tanzu CLI

During development phase 

```
kubectl apply -f workload.yaml
```

Once ready for uat

```
kubectl apply -f workload-uat.yaml
```

### Accessing the app deployed to your cluster

Determine the URL to use for accessing the app by running:

```
tanzu apps workload get WORKLOAD_NAME
```


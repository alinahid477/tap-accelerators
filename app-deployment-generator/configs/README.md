### Files in project

- Place the config folder in the root directory of application source code. 
- If you have generated configs for local development you will see a Tiltfile. Place this titlfile in the source code root directory. Adjust further if needs be.

### in CI/build cluster (cluster1)

```
kubectl apply -f build/workload.yaml
kubectl apply -f build/src-git-secret.yaml
```

The above command will create:
- a workload to connect to supplychain (CI pipeline) in the build cluster.
- a secret called src-git-secret-RPLC_WORKLOAD_NAME (refered in workload.yaml) for the supplychain to pull application source code.

To see the logs for supplychain execution run the below command:

```
tanzu apps workload tail RPLC_WORKLOAD_NAME --since 1h -n RPLC_NAMESPACE_NAME
```

### in CD/run cluster (cluster2)

```
kubectl apply -f run/deliverable.yaml
```

### local development (iteration using cluster1)
Pre-Requisites are:
- You have Tiltfile and Tilt tool installed in your local environment
- You are authenticated against in cluster1
- You have Tanzu Development plugin installed in your IDE (eclipse, vscode, visual studio)
- You have configured the settings for the tanzu development plugin. Here's a sample setting for vscode:
```{
    "tanzu.localPath": ".",
    "tanzu.namespace": "YOUR NAMESPACE NAME",
    "tanzu.trackedNamespaces": "YOUR NAMESPACE NAME"
}```

Once you have the prerequisites in place right click in the code pane and execute as necessary (eg: Tanzu: Live update start). 
This will deploy your local source code through the same supply chain into cluster1.
You will also be able to see the pods and logs and various CI steps logs from within your IDE (eg: in vscode Tanzu Activity tab in the terminal pane).

# File Generator for TAP

The following files are included:
- `workload-dev.yaml`: For dev supply chain
- `workload-uat.yaml`: For uat supply chain
- `catalog-info.yaml`: The definition of a Component to make the Workload available in the TAP GUI Catalog
- `DEPLOYING.md` : This file, providing instructions for preparing your project
- `Tiltfile` : A Tiltfile to enable Live Update and Debugging for Java Workloads using the TAP IDE Plugin (only provided if you selected to "Include TAP IDE Support for Java Workloads")

## Preparing your my-project project

Copy the provided `workload*.yaml` and `catalog-info.yaml` in the root directories of the `WORKLOAD_NAME` project. If a `Tiltfile` was included then copy it to the root directory of `WORKLOAD_NAME` project.

You can now follow the instructions in the `DEPLOYING.md` file to deploy your project.
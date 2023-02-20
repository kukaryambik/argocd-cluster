# ArgoCD Cluster

## File Structure & Naming Convention

### File Structure

The file structure is based on the K8S cluster structure and grouped by namespace; e.g.: [`cluster/argocd-example-apps/app_helm-guestbook.yaml`](./cluster/main/argocd-example-apps/app_helm-guestbook.yaml) for the `helm-guestbook` ArgoCD Application in the `argocd-example-apps` namespace.
The namespace level entities are located in the directories of these namespaces.
The cluster level entities are located in the `_cluster` directory.

**By default ArgoCD will prune resources if they are not tracked by Git anymore.**

### File Naming

File names should be constructed as follows: `<resourcetype>_<full-resource-name>.yaml`.
Only standard abbreviations and short resource names are allowed.
Example: `secret_gitlab-registry-creds.yaml` for Secret or `cm_my-app-envs.yaml` for ConfigMap.

### Exceptions

The only exception is namespace files. They are a cluster entity, but are located inside a namespace directory and named `_ns.yaml`.

# ArgoCD Cluster

## File Structure & Naming Convention

### File Structure

The Git repository contains the following directories under [cluster](./cluster/) and are ordered below by how ArgoCD will apply them.

- **`core`** directory is important infrastructure applications (grouped by namespace) that should never be pruned by ArgoCD.
- **`main`** directory is where the main content of the cluster (grouped by namespace) could be placed, ArgoCD will prune resources here if they are not tracked by Git anymore.

The file structure of each layer is based on the K8S cluster structure; e.g.: [`cluster/main/argocd-example-apps/app_helm-guestbook.yaml`](./cluster/main/argocd-example-apps/app_helm-guestbook.yaml) for the `helm-guestbook` ArgoCD Application in the `argocd-example-apps` namespace.
The namespace level entities are located in the directories of these namespaces.
The cluster level entities are located in the `_cluster` directory of each layer.

### File Naming

File names should be constructed as follows: `<resourcetype>_<full-resource-name>.yaml`.
Only standard abbreviations and short resource names are allowed.
Example: `secret_gitlab-registry-creds.yaml` for Secret or `cm_my-app-envs.yaml` for ConfigMap.

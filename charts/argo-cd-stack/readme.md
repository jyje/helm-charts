# jyje/argo-cd-stack

[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/jyje)](https://artifacthub.io/packages/search?repo=jyje)

Three Argo CD components are installed in this stack:
- Argo CD: The core Argo CD server
- Argo CD Application Set: Initial Release for Argo CD (Applications or Projects)
- Argo CD Image Updater: Automatically update the container images in a Kubernetes cluster

The release name should be `argocd`. There is a mismatch between the names `argocd` and `argo-cd`, which is causing ambiguity. So we override the `fullnameOverride` for the Argo CD Helm Chart to `argocd`.

## Warning: This is not a official Helm Chart

⚠️ This is a collection of Helm Charts for Argo CD components. The official Helm Chart for Argo CD is available at [argoproj/argo-helm](https://github.com/argoproj/argo-helm).

## How to install

```bash
helm repo add jyje https://jyje.github.io/helm-charts/charts
helm repo update

helm upgrade --install \
    --namespace argocd --create-namespace \
    argocd jyje/argo-cd-stack
```



## Parameters

| Parameter | Description | References / Overrided Values |
|-----------|-------------|---------|
| argo-cd.* | Argo CD Helm Chart values | https://github.com/argoproj/argo-helm/tree/main/charts/argo-cd |
| argocd-apps.* | Argo CD Application Set Helm Chart values | https://github.com/argoproj/argo-helm/tree/main/charts/argocd-apps |
| argocd-image-updater.* | Argo CD Image Updater Helm Chart values | https://github.com/argoproj/argo-helm/tree/main/charts/argocd-image-updater 
| argo-cd.fullnameOverride | Full name of the Argo CD Helm Chart | `argocd` |
| argocd-image-updater.fullnameOverride | Full name of the Argo CD Image Updater Helm Chart | `argocd-image-updater` |

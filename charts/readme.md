# jyje/helm-charts

[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/jyje)](https://artifacthub.io/packages/search?repo=jyje)

## Helm Charts by jyje

This repository contains useful Helm Charts for Kubernetes curated by jyje.

```sh
helm repo add jyje https://jyje.github.io/helm-charts/charts
helm repo update
```

## Charts

- [argo-cd-stack](argo-cd-stack/readme.md): Stack of Argo CD components


## How to update

### Update repository index

At root directory, run:
```sh
cd charts
helm package .
helm repo index . --merge index.yaml
```

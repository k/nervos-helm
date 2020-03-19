# Handshake Helm Charts

This is an unofficial registry of [Nervos](https://nervos.org/) [helm](https://helm.sh/) charts.

## Prerequisites
* [Helm](https://helm.sh/) 3+

## Setup

Add the nervos helm repo:
```
helm repo add nervos https://k.github.io/nervos-helm
helm repo update
```

Then configure a values.yaml for the chart you want to install.

## List of Charts

### [CKB](./charts/ckb)

Chart to run a Nervos CKB Full Node

## Deploy to Github Pages

Deploy requires [`cr`](https://github.com/helm/chart-releaser) tool 

### Package chart

```
helm package charts/<chart-to-package> --destination .deploy
```

### Upload New Release

```
cr upload --config config.yaml --token <deploy-token>
```

### Generate new index
```
cr index --config config.yaml
git add index.yaml
git commit -m "Update index.yaml"
git push
```

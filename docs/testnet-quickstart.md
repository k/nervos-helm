# Aggron Testnet Quickstart

Get a CKB full node running on the testnet in 5 minutes

## Install Minikube and Helm

```
brew install helm minikube
```

## Add Nervos helm repository

```
helm repo add nervos https://k.github.io/nervos-helm
helm repo update
```

## Create local minikube Cluster for Nervos

```
minikube start --profile nervos
```

## Install Nervos Aggron Node

```
helm install ckb nervos/ckb
```

## View logs

```
kubectl get pods            # Wait until pods are ready
kubectl logs ckb-0 --follow # view the logs, you should see the node syncing
```

## Port-forward to your Full Node

```
kubectl port-forward svc/ckb 8114
```

Your node is now available at http://localhost:8114

Try communicating with your ckb node via [ckb-cli](https://github.com/nervosnetwork/ckb-cli)!

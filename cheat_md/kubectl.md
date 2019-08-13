# Kubectl

## List namespaces :
```bash
kubectl get ns
```

## List all pod within a namespace :
```bash
kubectl get all -n <namespace>
```
## Get info of pod
```bash 
kubectl describe <podname> -n namespace
```
## Show namespaces
```bash
kubens
```
## Show clusters
```bash
kubectx 
```
## start proxy :
```
kubectl proxy
```

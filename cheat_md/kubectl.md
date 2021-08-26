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

## Run busybox :
```
kubectl run -i --tty busybox --image=busybox --restart=Never -- sh
```

## Generate yaml file without applying the command ( dry run uno )
```
kubectl create deployment --image peepoodo test -o yaml --dry-run=client
```

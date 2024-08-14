# critcl tips


## Shell into a pod with root privileges ( even if it's a non-root container )

```
runc --root /run/containerd/runc/k8s.io/ exec -t -u 0 <container ID>
```

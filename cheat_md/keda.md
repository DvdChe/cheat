# Keda tips and tricks:

## Pause scaledobject and force replicas number

```bash
kubectl patch scaledobject <scaledobject-name>  --type='merge' -p \
  '{"metadata": {"annotations":{
     "autoscaling.keda.sh/paused-replicas":"0",
     "autoscaling.keda.sh/paused": "true"
    }}}'
```

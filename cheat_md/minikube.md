# Minikube cheat


Get nodeport of a service:
```
   minikube service --url <service> -n <namespace of the service>
```

note : services can be seen by `kubectl get svc`

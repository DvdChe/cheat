# Helm trics :


## Run chart and show render of all elements to stdout
```
helm install repo/chart --dry-run --debug --generate-name
```


## Parse template and show rendering to stdout
```
helm template template.yaml -f values.yaml 
```

## Get manifests from deployed chart 
```
helm get manifests <release>
```

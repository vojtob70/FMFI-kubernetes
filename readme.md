# FMFI kubernetes

## Kind homepage
https://kind.sigs.k8s.io/

### Prereqs
- docker installed  (https://www.docker.com)
- go installed  (https://golang.org)
- kind installed 
```bash
go install sigs.k8s.io/kind@v0.16.0
```

### create kubernetes cluster by kind with ingress ready
```bash
kind delete cluster
bash ./kind.create.cluster.sh
```

### add ingress 

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
```

### add test-deployment
```bash
kubectl apply -f test-deployment.yaml
```

### add test-service
```bash
kubectl apply -f test-service.yaml
```

### add test-ingress
```bash
kubectl apply -f test-ingress.yaml
```

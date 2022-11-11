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

### add http-echo app
```bash
kubectl apply -f http-echo
```
http://localhost:5678

### add webcolor
```bash
kubectl apply -f webcolor
```
http://localhost:8888

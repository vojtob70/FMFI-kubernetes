# Kind homepage
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
cat <<EOF | kind create cluster --config=-
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
  kubeadmConfigPatches:
  - |
    kind: InitConfiguration
    nodeRegistration:
      kubeletExtraArgs:
        node-labels: "ingress-ready=true"
  extraPortMappings:
  - containerPort: 80
    hostPort: 80
    protocol: TCP
  - containerPort: 443
    hostPort: 443
    protocol: TCP
EOF
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

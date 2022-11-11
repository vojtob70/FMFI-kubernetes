# FMFI kubernetes

## Kind homepage
https://kind.sigs.k8s.io/

### Prereqs
- docker installed  (https://www.docker.com)
```bash
https://docs.docker.com/desktop/install/windows-install/
```
- go installed  (https://golang.org)
```bash
https://go.dev/dl/go1.19.3.windows-amd64.msi
```
- kind installed 
```bash
choco install kind
```
- kubectl for Windows
```bash
choco install kubernetes-cli
```
- chocolatey install
```bash
https://chocolatey.org/install
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

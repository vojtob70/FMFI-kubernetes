# FMFI kubernetes

## Kind homepage
https://kind.sigs.k8s.io/

### Test pripravenosti
```
echo '---------  docker  --------------'
docker version
echo
echo '------------  go  ---------------'
go version
echo
echo '-----------  kind  --------------'
kind version
echo
echo '----------- kubectl -------------'
kubectl version
```

### Instalacia dockera (https://www.docker.com)

### Instalacia go (https://golang.org)
```
wget https://go.dev/dl/go1.19.4.linux-amd64.tar.gz
```
go instalovat podla postupu https://go.dev/doc/install
```
sudo rm -rf /usr/local/go && sudo tar -C /usr/local -xzf go1.19.4.linux-amd64.tar.gz
```

### Instalacia Kind kubernetesu
```bash
go install sigs.k8s.io/kind@v0.16.0
```

do premennej prostredia PATH pridat:
```
echo $(go env GOPATH)/bin
```

### Instalacia kubectl nastroja (https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)
```
curl -LO https://dl.k8s.io/release/v1.25.0/bin/linux/amd64/kubectl
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
kubectl version --client
```

### create kubernetes cluster by kind with ingress ready
```bash
kind delete cluster
bash ./kind.create.cluster.sh
```

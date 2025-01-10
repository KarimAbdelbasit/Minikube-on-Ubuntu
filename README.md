# Minikube-on-Ubuntu
Installing Minikube on Ubuntu
### Step 1. Installing Docker
```
sudo apt update
sudo apt install apt-transport-https curl
sudo apt install docker.io
sudo systemctl enable docker
sudo systemctl start docker
docker --version
```
### Step 2. Updating system packages and installing Minikube dependencies
```
sudo apt update
```
```
sudo apt install -y curl wget apt-transport-https
```
### Step 3. Installing Minikube
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
```
```
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```
### Step 4. Verifying Minikube installation
```
minikube version
```
### Step 5. Installing kubectl utility
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
```
```
chmod +x kubectl
```
```
sudo mv kubectl /usr/local/bin/
```
### Step 6. verify the kubectl version
```
kubectl version -o yaml
```
# Output
```
clientVersion:
 buildDate: "2023–11–15T16:58:22Z"
 compiler: gc
 gitCommit: bae2c62678db2b5053817bc97181fcc2e8388103
 gitTreeState: clean
 gitVersion: v1.28.4
 goVersion: go1.20.11
 major: "1"
 minor: "28"
 platform: linux/amd64
kustomizeVersion: v5.0.4–0.20230601165947–6ce0bf390ce3
serverVersion:
 buildDate: "2023–10–18T11:33:18Z"
 compiler: gc
 gitCommit: a8a1abc25cad87333840cd7d54be2efaf31a3177
 gitTreeState: clean
 gitVersion: v1.28.3
 goVersion: go1.20.10
 major: "1"
 minor: "28"
 platform: linux/amd64
```
### Step 7. Starting Minikube
```
minikube start — driver=docker
```
### Step 8. Verifying Installation
```
minikube status
```
# Output
```
minikube
type: Control Plane
host: Running
kubelet: Running
apiserver: Running
kubeconfig: Configured
```

### Step 9. Use the following command to verify Kubernetes:
```
kubectl cluster-info
```
# Output
```
Kubernetes control plane is running at https://192.168.49.2:8443
CoreDNS is running at https://192.168.49.2:8443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
```


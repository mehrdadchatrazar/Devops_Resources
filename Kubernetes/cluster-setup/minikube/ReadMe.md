# [minikube start](https://minikube.sigs.k8s.io/docs/start/)
minikube is local Kubernetes, focusing on making it easy to learn and develop for Kubernetes.


#
#### What you’ll need
- 2 CPUs or more
- 2GB of free memory
- 20GB of free disk space
- Internet connection
- Container or virtual machine manager, such as: Docker, QEMU, Hyperkit, Hyper-V, KVM, Parallels, Podman, VirtualBox, or VMware Fusion/Workstation


#
### Installation

To install the latest minikube stable release on x86-64 Linux using Debian package:

``` 
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube_latest_amd64.deb
sudo dpkg -i minikube_latest_amd64.deb
```


#
### Start your cluster
```
minikube start
```
### to use mirror registry:
```
minikube start --registry-mirror="https://docker.arvancloud.ir" --insecure-registry="https://docker.arvancloud.ir"
```


#
### Interact with your cluster

If you already have kubectl installed, you can now use it to access your shiny new cluster:
```
kubectl get po -A
```

### Install `kvm`
```
sudo apt install libvirt-bin qemu-kvm -y
```
### Add user to `libvirtd` group
```
sudo usermod -aG libvirtd $(whoami)
# re-ssh to take effect
```
### Install `kubectl`
```
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
echo "deb http://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
sudo apt update
sudo apt -y install kubectl
```
### Install `kvm2` driver
```
curl -LO https://storage.googleapis.com/minikube/releases/v0.30.0/docker-machine-driver-kvm2
chmod +x docker-machine-driver-kvm2
sudo mv docker-machine-driver-kvm2 /usr/local/bin/
```
### Install `minikube`
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
chmod +x minikube-linux-amd64
sudo mv minikube-linux-amd64 /usr/local/bin/minikube
```
### Start
```
minikube config set vm-driver kvm2
minikube start
```

Master hostname (master-node)
worker node1 (worker-node1)
worker node2 (worker-node2)


You must be a root user on all nodes to perform the following tasks:
$ sudo su -

STEP-1:
# vim /etc/modules-load.d/containerd.conf

Insert following in file:
overlay
br_netfilter

save file and run these command:
# modprobe overlay
# modprobe br_netfilter

STEP-2:
# vim /etc/sysctl.d/kubernetes.conf

Insert following in file:

net.bridge.bridge-nf-call-ip6tables = 1
net.bridge.bridge-nf-call-iptables = 1
net.ipv4.ip_forward = 1

save file and run this command:
# sysctl --system
# sysctl -p


STEP-3
Run following commands to enable docker repository:
# curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
# add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"



Install containerd in all nodes
# apt update 


# apt install -y containerd.io
# rm -f /etc/containerd/config.toml
# systemctl daemon-reload
# systemctl start containerd
# systemctl enable containerd
# systemctl status containerd

STEP-4
Add kubernetes repository in all nodes
# apt-get update && apt-get install -y apt-transport-https ca-certificates curl

# curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg

# echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list

STEP-5
Disable swap:
# vim /etc/fstab (Remove swap mount point from this file)
# swapoff -a

##done on w2 and um

STEP-6
Export the environment variable:
# export KUBE_VERSION=1.23.0

Install kubernetes:
# apt-get update

# apt-get install -y kubelet=${KUBE_VERSION}-00 kubeadm=${KUBE_VERSION}-00 kubectl=${KUBE_VERSION}-00 kubernetes-cni=0.8.7-00

# apt-mark hold kubelet kubeadm kubectl (Secure the packages for accidental removal)
# systemctl enable kubelet
# systemctl start kubelet

#M

STEP-7 - Master 
# kubeadm init --kubernetes-version=${KUBE_VERSION} (Only on master node)
# kubeadm token create --print-join-command (To regenrate the tokens)

STEP-8 - Master 
# cp /etc/kubernetes/admin.conf /root/
# chown $(id -u):$(id -g) /root/admin.conf
# export KUBECONFIG=/root/admin.conf
# echo 'export KUBECONFIG=/root/admin.conf' >> /root/.bashrc
# exit

STEP-9 - Master 
# kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')" 
OR
https://github.com/weaveworks/weave/releases
Download the daemonset yaml file of required version like following link. 
wget https://github.com/weaveworks/weave/releases/download/v2.8.1/weave-daemonset-k8s.yaml
then 
# kubectl apply -f weave-daemonset-k8s.yaml




===============

## Change IP in ubuntu
sudo nano /etc/netplan/00-installer-config.yaml

network:
  version: 2
  renderer: networkd
  ethernets:
    ens160:
      dhcp4: no
      dhcp6: no
      addresses: 
        - 172.21.74.XXX/24
      gateway4: 172.21.74.1
      nameservers:
              addresses: [8.8.8.8,8.8.4.4]


sudo netplan try
sudo netplan apply
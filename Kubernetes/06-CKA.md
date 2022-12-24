# CKA


kubeadm join 172.21.74.153:6443 --token pjwikb.fxn0l5zs8y67zwo9 \
        --discovery-token-ca-cert-hash sha256:8ce17bec574292a2d3f39a65eb31b3516b2b42929f56e76ff6109fa5858a0eee



[addons] Applied essential addon: kube-proxy

Your Kubernetes control-plane has initialized successfully!

To start using your cluster, you need to run the following as a regular user:

  mkdir -p $HOME/.kube
  sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
  sudo chown $(id -u):$(id -g) $HOME/.kube/config

Alternatively, if you are the root user, you can run:

  export KUBECONFIG=/etc/kubernetes/admin.conf

You should now deploy a pod network to the cluster.
Run "kubectl apply -f [podnetwork].yaml" with one of the options listed at:
  https://kubernetes.io/docs/concepts/cluster-administration/addons/

Then you can join any number of worker nodes by running the following on each as root:

kubeadm join 172.21.74.153:6443 --token pjwikb.fxn0l5zs8y67zwo9 \
        --discovery-token-ca-cert-hash sha256:8ce17bec574292a2d3f39a65eb31b3516b2b42929f56e76ff6109fa5858a0eee
root@cka-master:~#
root@cka-master:~#
root@cka-master:~#
root@cka-master:~#
root@cka-master:~# kubectl get nodes
The connection to the server localhost:8080 was refused - did you specify the right host or port?
root@cka-master:~#



====
cred

cka-master/12345

===

- containerd & kubelet is not containerized {installed as service on system}
- All communication 

`crictl images` for checking images on container io  

======
cka-master 172.21.74.153
cka-worker-01 172.21.74.203
cka-worker-02 172.21.74.253

SERVER
PC            172.21.74.3
Master Jenkins 172.21.74.53
Worker-01         172.21.74.103
Worker-02         172.21.74.103


LOCAL
cka-master    172.21.74.153
cka-worker-01 172.21.74.203
cka-worker-02 172.21.74.253


cka-master    192.168.144.133
cka-worker-01 192.168.144.134
cka-worker-02 
# kubernetes_install_AWS
Install kubernetes on aws with 3 node cluster(1 master and 2 workers)

Initialize a Kubernetes cluster using the kubeadm

$ kubeadm init --pod-network-cidr=10.244.0.0/16

install CNI	

$ kubectl apply -f https://raw.githubusercontent.com/flannel-io/flannel/master/Documentation/kube-flannel.yml

To start using your cluster, you need to run the following as a regular user 
$ mkdir -p $HOME/.kube 
$ sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config 
$ sudo chown ( i d − u ) : (id -g) $HOME/.kube/config kubectl taint nodes --all node-role.kubernetes.io/control-plane-

<img width="2418" height="936" alt="image" src="https://github.com/user-attachments/assets/040bcae3-c906-428e-9c1a-6062838f741c" />

Make sure to enable 6443 port in the security group


Create token to join the cluster.

kubeadm token create --print-join-command

Join the cluster - Change the ip of your master node. (copy the token and run it on the worker nodes)

change the worker node labels by the command

<img width="2512" height="354" alt="image" src="https://github.com/user-attachments/assets/282aaab8-9835-4c1f-9f33-ad368bc7a2f8" />

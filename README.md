# kubernetes setup using ansible and vagrant

This contains the working code to setup kubernetes using anisble and vagrant.

> adheres to offical documentation : https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/

## Prerequistes
* Vagrant should be installed on your machine. Installation binaries can be found [here](https://www.vagrantup.com/downloads.html).
* Oracle VirtualBox can be used as a Vagrant provider or make use of similar providers as described in Vagrant's official [documentation](https://www.vagrantup.com/docs/providers/).
* Ansible should be installed in your machine. Refer to the [Ansible installation guide](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) for platform specific installation.

## How to use

1. Clone repo
```bash
git clone https://github.com/naveenrajm7/k8s-setup.git
```

2. Execute vagrant inside folder
```bash
cd k8s-setup
vagrant up
```

3. Access master and use kubernetes
```bash
$ ## Accessing master
$ vagrant ssh k8s-master
vagrant@k8s-master:~$ kubectl get nodes
NAME         STATUS   ROLES                  AGE     VERSION
k8s-master   Ready    control-plane,master   14m     v1.23.3
node-1       Ready    <none>                 9m37s   v1.23.3
node-2       Ready    <none>                 5m19s   v1.23.3

vagrant@k8s-master:~$ kubectl create ns my-ns
namespace/my-ns created
```


### To connect to kuberenetes cluster from outside the cluster.

* Copy ~/.kube/config to host machine  
https://www.alexkras.com/how-to-copy-one-file-from-vagrant-virtual-machine-to-local-host/

* Make sure the ip address of vagrant VMs are reachable
https://www.vagrantup.com/docs/networking/private_network.html

* Make sure you are not in a VPN , as this will make VM IPs unreachable.


## Reference

* [kubernetes-setup-using-ansible-and-vagrant](https://kubernetes.io/blog/2019/03/15/kubernetes-setup-using-ansible-and-vagrant/)


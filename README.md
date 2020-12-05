# kubernetes setup using ansible and vagrant

This contains the working code to setup kubernetes using anisble and vagrant as shown in [blog](https://kubernetes.io/blog/2019/03/15/kubernetes-setup-using-ansible-and-vagrant/)

## Prerequistes
* Vagrant should be installed on your machine. Installation binaries can be found [here](https://www.vagrantup.com/downloads.html).
* Oracle VirtualBox can be used as a Vagrant provider or make use of similar providers as described in Vagrant's official [documentation](https://www.vagrantup.com/docs/providers/).
* Ansible should be installed in your machine. Refer to the [Ansible installation guide](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) for platform specific installation.

## How to use

1. Clone repo
```bash
git clone k8s-setup
```

2. Execute vagrant inside folder
```bash
cd k8s-setup
vagrant up
```

3. Access master and nodes
```bash
$ ## Accessing master
$ vagrant ssh k8s-master
vagrant@k8s-master:~$ kubectl get nodes
NAME         STATUS   ROLES    AGE   VERSION
k8s-master   Ready    master   40m   v1.19.4
node-1       Ready    <none>   36m   v1.19.4
node-2       Ready    <none>   32m   v1.19.4

$ ## Accessing nodes
$ vagrant ssh node-1
$ vagrant ssh node-2
```




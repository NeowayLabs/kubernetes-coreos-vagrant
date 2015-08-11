Kubernetes on CoreOS with Vagrant
=================================

Vagrant create [Kubernetes] Cluster on [Coreos], with one master and two nodes (minions)

> **Master IP:** 192.168.33.10

> **Node01 IP:** 192.168.33.11

> **Node02 IP:** 192.168.33.12

> **Flannel:** 10.244.0.0/16

> **Cluster CIDR:** 10.100.0.0/16

### Usage

#### Install [Vagrant]

#### Install [VirtualBox]

#### Install [Kubernetes]

#### Clone this repo and:

        cd kubernetes-coreos-vagrant
        vagrant up


### Kubernetes basic

#### Get nodes

        kubectl -s http://192.168.33.10:8080 get nodes



[CoreOS]:https://coreos.com
[Vagrant]:https://www.vagrantup.com/
[Virtualbox]:https://www.virtualbox.com/
[Kubernetes]:http://kubernetes.io/

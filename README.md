Kubernetes on CoreOS with Vagrant
=================================

Vagrant create [Kubernetes] Cluster on [Coreos], with one master and two nodes (minions)

> **Master IP:** 192.168.33.10

> **Node1 IP:** Master IP +1

> **Node2 IP:** Master IP +2

> **NodeN IP:** Master IP +n

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
        kubectl -s http://192.168.33.10:8080 create -f k8s/rc/nginx.yaml
        kubectl -s http://192.168.33.10:8080 create -f k8s/svc/nginx.yml

        kubectl -s http://192.168.33.10:8080 create -f k8s/rc/kube-ui-rc.yaml
        kubectl -s http://192.168.33.10:8080 create -f k8s/svc/kube-ui-svc.yaml

        kubectl -s http://192.168.33.10:8080 get pods
        kubectl -s http://192.168.33.10:8080 get services
        kubectl -s http://192.168.33.10:8080 get endpoints



[CoreOS]:https://coreos.com
[Vagrant]:https://www.vagrantup.com/
[Virtualbox]:https://www.virtualbox.com/
[Kubernetes]:http://kubernetes.io/

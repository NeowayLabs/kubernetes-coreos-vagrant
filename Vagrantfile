# -*- mode: ruby -*-
# vi: set ft=ruby :

NODES=3
BASE_IP_ADDR="192.168.33"
MASTER_IP="#{BASE_IP_ADDR}.10"

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "coreos-stable"
  config.vm.box_url = "http://stable.release.core-os.net/amd64-usr/current/coreos_production_vagrant.json"
  config.vm.box_check_update = true

  config.vm.define "master" do |master|
    master.vm.network "private_network", ip: "#{MASTER_IP}"
    master.vm.provision :file, :source => "cloud-config/master.yaml", :destination => "/tmp/vagrantfile-user-data"
    master.vm.provision :shell, :inline => "mv /tmp/vagrantfile-user-data /var/lib/coreos-vagrant/", :privileged => true
  end

  (1..(NODES.to_i)).each do |i|
    config.vm.define "node#{i}" do |node|
      node.vm.network "private_network", ip: "#{BASE_IP_ADDR}.#{i+10}"
      node.vm.provision :file, :source => "cloud-config/node.yaml", :destination => "/tmp/vagrantfile-user-data"
      node.vm.provision :shell, :inline => "mv /tmp/vagrantfile-user-data /var/lib/coreos-vagrant/", :privileged => true
    end
  end

end

# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "coreos-stable"
  config.vm.box_url = "http://stable.release.core-os.net/amd64-usr/current/coreos_production_vagrant.json"
  config.vm.box_check_update = true

  config.vm.define "master" do |master|
    master.vm.network "private_network", ip: "192.168.33.10"
    master.vm.provision :file, :source => "cloud-config/master.yaml", :destination => "/tmp/vagrantfile-user-data"
    master.vm.provision :shell, :inline => "mv /tmp/vagrantfile-user-data /var/lib/coreos-vagrant/", :privileged => true
  end

  config.vm.define "node01" do |node01|
    node01.vm.network "private_network", ip: "192.168.33.11"
    node01.vm.provision :file, :source => "cloud-config/node.yaml", :destination => "/tmp/vagrantfile-user-data"
    node01.vm.provision :shell, :inline => "mv /tmp/vagrantfile-user-data /var/lib/coreos-vagrant/", :privileged => true
  end

  config.vm.define "node02" do |node02|
    node02.vm.network "private_network", ip: "192.168.33.12"
    node02.vm.provision :file, :source => "cloud-config/node.yaml", :destination => "/tmp/vagrantfile-user-data"
    node02.vm.provision :shell, :inline => "mv /tmp/vagrantfile-user-data /var/lib/coreos-vagrant/", :privileged => true
  end

end

# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |vps|
  vps.vm.box = "debian/bullseye64"
  vps.vm.hostname = "nuvemlgbt-vagrant-docker"
  vps.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 2
    v.default_nic_type = "virtio"
    v.customize ["modifyvm", :id, "--natnet1", "10.254.0.0/16"]
  end
end

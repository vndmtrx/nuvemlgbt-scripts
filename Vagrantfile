# -*- mode: ruby -*-
# vi: set ft=ruby :

$msg = <<MSG
------------------------------------------------------
NuvemLGBT local

Instalação de desenvolvimento e testes usando Vagrant
e Ansible.
------------------------------------------------------
MSG

Vagrant.configure("2") do |vps|
  vps.vm.box = "debian/bullseye64"
  vps.vm.hostname = "nuvemlgbt-vagrant-docker"
  vps.vm.network "private_network", :ip => "192.168.56.10", :adapter => 2
  vps.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 4
    v.default_nic_type = "virtio"
    v.customize ["modifyvm", :id, "--natnet1", "10.254.0.0/16"]
  end

  vps.vm.provision :"ansible" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.config_file = "ansible/.ansible.cfg"
  end

  vps.vm.post_up_message = $msg
end

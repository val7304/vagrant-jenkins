# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"   # Ubuntu 20.04 LTS

  config.vm.hostname = "jenkins-vm"
  config.vm.network "private_network", ip: "192.168.56.10"
  config.vm.synced_folder ".", "/vagrant"
  
  # Provision Ansible_local
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "/vagrant/ansible/install_jenkins.yml"
  end

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = 2
  end
end

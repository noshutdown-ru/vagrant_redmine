# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.ssh.private_key_path = ["./vagrant","~/.vagrant.d/insecure_private_key"]
  config.vm.provision "file", source: "./vagrant.pub", destination: "~/.ssh/authorized_keys"
  config.vm.network "private_network", type: "dhcp"
  
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.verbose = "v"
  end

  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 2
    vb.memory = "1024"
    vb.name = "redmine-server"
  end
end

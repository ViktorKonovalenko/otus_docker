# -*- mode: ruby -*- 
# vi: set ft=ruby : vsa
Vagrant.configure(2) do |config| 
 config.vm.box = "centos/7" 
# config.vm.box_version = "2004.01" 
 config.vm.provider "virtualbox" do |v| 
 v.memory = 256 
 v.cpus = 1 
 end 
 config.vm.define "docker" do |docker| 
 docker.vm.network "private_network", ip: "192.168.56.10",  virtualbox__intnet: "net1" 
 docker.vm.hostname = "docker" 
 docker.vm.network "forwarded_port", guest: 8080, host: 80
 end 
 config.vm.provision "ansible" do |ansible|
 ansible.playbook = "playbook-docker.yml"
 ansible.become = "true"
 end
end 

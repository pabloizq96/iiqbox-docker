# -*- mode: ruby -*-
# vi: set ft=ruby :
hostname = "iiqbox-docker"
memory = 8192
cpus = 4
Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/centos8"
  config.vm.hostname = hostname
  config.vm.define hostname
  config.vm.network "private_network", ip: "10.0.0.10"
  config.vm.network "forwarded_port", guest:8080, host:8080
  config.vm.network "forwarded_port", guest:8001, host:8001
  config.vm.network "forwarded_port", guest:8025, host:8025
  config.vm.network "forwarded_port", guest:3306, host:3306

  config.vbguest.installer_options = { allow_kernel_upgrade: true }

  config.vm.provider "virtualbox" do |vb|
    vb.name = hostname
    vb.memory = memory
    vb.cpus = cpus
  end

  config.vm.provision :docker
  config.vm.provision :docker_compose, yml: "/vagrant/docker-compose.yml", run: "always"
end

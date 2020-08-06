# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.hostname = "ed-ubuntu-docker-box"
  config.vm.box = "bento/ubuntu-20.04"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network "private_network", ip: "192.168.50.100"

  config.vm.synced_folder "/workspace/", "/workspace"
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider "virtualbox" do |vb|
    vb.name = 'ed-ubuntu-docker-vm'
    vb.memory = 4096
    vb.cpus = 2
  end

  config.vm.provision :docker

  config.vm.post_up_message = "Box is successfully provisioned :)"
end
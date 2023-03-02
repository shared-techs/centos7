# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  
  config.vm.box = "prlabwork/centos7base"
  config.vm.hostname = "dockerhost"
  config.vm.define "dockerhost"

  config.vm.network :private_network, type: "dhcp", ip: "192.168.3.6"
  config.vm.network "public_network"

  config.vm.synced_folder "./share", "/home/vagrant/share", type: "rsync"
  config.vm.network :forwarded_port, host: 80, guest: 80
  # config.vm.provider "virtualbox" do |vb|
  #   vb.memory = "4096"
  # end
   
  config.vm.provision :shell, path: "./install.sh"
   
end

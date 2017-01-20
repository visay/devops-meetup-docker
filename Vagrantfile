# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.require_version ">= 1.9.1"

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"
  config.vm.box_check_update = false
  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "1024"
  end

end

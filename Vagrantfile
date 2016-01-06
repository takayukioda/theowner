# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  [
    { name: "nrel/CentOS-6.6-x86_64", alias: "centos", addr: "10" },
    { name: "trusty64", alias: "ubuntu", addr: "11" }
  ].each do |box|
    config.vm.define box[:alias] do |server|
      server.vm.box = box[:name]
      server.vm.hostname = box[:alias]
      server.vm.network "private_network", ip: "192.168.99." + box[:addr]
    end
  end
  config.vm.box = "nrel/CentOS-6.6-x86_64"

  config.vm.provider "virtualbox" do |vb|
    # Customize the amount of memory on the VM:
    vb.memory = "1024"
  end

end

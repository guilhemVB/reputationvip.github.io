# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty32"

  config.ssh.forward_agent = true

  config.vm.network :private_network, ip: "192.168.33.111"
  config.vm.network "forwarded_port", guest: 4000, host: 4000, auto_correct: true

  config.vm.provider "virtualbox" do |vb|
     vb.customize ["modifyvm", :id, "--memory", "512"]
  end

  config.vm.provision "shell", path: "scripts/provisionning.sh"
end

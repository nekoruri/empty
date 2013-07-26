# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "precise32"
  config.vm.box_url = "http://files.vagrantup.com/precise32.box"
  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.network :private_network, ip: "192.168.33.10"
  config.ssh.forward_agent = true
  config.vm.synced_folder ".", "/app"

  config.vm.provision :shell, :inline => "apt-get update; DEBIAN_FRONTEND=noninteractive apt-get install -y libsqlite3-dev ruby1.9.3 build-essential && /usr/bin/gem1.9.3 install bundler"
end

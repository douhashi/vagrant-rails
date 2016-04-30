# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu1404"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"

  config.vm.hostname = "vagrant-rails"
  config.vm.network :forwarded_port, guest: 22, host: 2001, id: "ssh"
  config.vm.network :private_network, ip: "192.168.33.11"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 1024
  end

  config.vm.provision :shell do |sh|
    sh.path = "provision.sh"
    sh.args = "provisioning/site.yml provisioning/development"
  end
end

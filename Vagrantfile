# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "hashicorp/precise64"

  config.vm.network "forwarded_port", guest: 8080, host: 8080

  config.vm.provision :docker do |d|
    d.pull_images "ubuntu"
  end

  config.vm.provision :shell, path: "scripts/vagrant.sh"

  config.vm.synced_folder 'ansible', '/vagrant/ansible', mount_options: ["fmode=666"]

  config.vm.provider :virtualbox do |vb|
    vb.memory = 2024
    vb.cpus = 2
  end

end

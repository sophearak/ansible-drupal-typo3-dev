# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

aliasesPath = File.expand_path("./scripts/aliases")

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "bandanh"

  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.network "private_network", ip: "192.168.33.11"


  config.vm.synced_folder "./www", "/var/www", id: "vagrant-root",
      owner: "vagrant",
      group: "www-data",
      mount_options: ["dmode=775,fmode=664"]

  if File.exists? aliasesPath then
      config.vm.provision "file", source: aliasesPath, destination: "~/.bash_aliases"
  end
end

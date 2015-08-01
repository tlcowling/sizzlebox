# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  config.vm.define "sizzlebox" do |sizzlebox|
    sizzlebox.vm.box         = "puppetlabs/centos-6.6-64-puppet"
    sizzlebox.vm.hostname    = "sizzlebox"
    sizzlebox.vm.synced_folder "certs/", "/etc/ssl"
    #sizzlebox.vm.network       "private_network", ip: "192.168.100.10"
    sizzlebox.vm.network       "forwarded_port", host: 8080, guest: 80
    sizzlebox.vm.network       "forwarded_port", host: 8443, guest: 443

    # Enable provisioning with a shell script. Additional provisioners such as
    # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
    # documentation for more information about their specific syntax and use.
    sizzlebox.vm.provision "puppet" do |puppet|
      puppet.manifests_path = "./"
      puppet.module_path   = "./modules"
      puppet.manifest_file = "provision.pp"
      puppet.hiera_config_path = "./hiera.yaml"
    end
  end 
end

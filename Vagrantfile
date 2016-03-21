# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.define "graphy" do |graphy|
    graphy.vm.box = "ubuntu/trusty64"
    graphy.vm.hostname = "graphy"

    graphy.vm.network "forwarded_port", guest: 7474, host: 7474

    graphy.vm.synced_folder "/home/viking/Downloads/", "/home/vagrant/Downloads"
    graphy.ssh.forward_x11 = true

    graphy.vm.provision "ansible" do |ansible|
        # ansible.verbose = "v"
        ansible.playbook = "site.yml"
        # ansible.galaxy_role_file = "roles.yml"
        ansible.galaxy_roles_path = "roles/"
    end
  end

end

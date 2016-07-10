## Boilerplate Vagrantfile for Salt-provisioned boxes. 

Vagrant.configure(2) do |config|

  config.vm.box = "debian/jessie64"

  # For masterless configuration:
  config.vm.synced_folder "salt/file_roots/", "/srv/salt/"
  config.vm.synced_folder "salt/pillar_roots/", "/srv/pillar/"
  config.vm.synced_folder "salt/minion.d/", "/etc/salt/minion.d/"

  # Configure Salt provisioning:
  config.vm.provision :salt do |salt|

    salt.install_type = "stable"
    salt.masterless = true
    salt.minion_config = "salt/minion"
    salt.run_highstate = true
    salt.grains_config = "salt/minion.d/vagrant.conf"

  end
end

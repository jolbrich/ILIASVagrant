Vagrant.configure("2") do |config|

  # Enable the Puppet provisioner, with will look in manifests
  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "manifests"
    puppet.manifest_file = "default.pp"
    puppet.module_path = "modules"
  end

  config.vm.provider "virtualbox" do |v|
    v.name = "ILIAS dev on Ubuntu 14.04"
  end

  config.vm.define "iliasdev14.04" do |dummy|
  end

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "ubuntu/trusty32" 

  # Forward guest port 80 to host port 8888 and name mapping
  config.vm.network :forwarded_port, guest: 80, host: 8888

  config.vm.synced_folder "shared/", "/opt/ilias/shared", :owner => "www-data", group: "www-data"
end

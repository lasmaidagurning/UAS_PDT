# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.define "ng1" do |ng1|
	ng1.vm.box = "ubuntu/trusty64"
	ng1.vm.network "private_network", ip: "10.0.0.10"
	ng1.vm.provision "shell", path:
"https://gist.githubusercontent.com/abraunton/263a1796578ebc487af8/raw/7da0dced1083610bf3275a9fae3dca05bf0ae51a/provision-lb.sh"
end

config.vm.define "web1" do |web1|
	web1.vm.box = "ubuntu/trusty64"
	web1.vm.network "private_network", ip: "10.0.0.11"
	web1.vm.provision :shell do |shell|
	shell.args = "1"
	shell.path =

"https://gist.githubusercontent.com/abraunton/1bfbf0aba866baa3b1fa/raw/df07f5001ce7296bc6e663f0fd68cbf5c89b9959/provision-web.sh"
	end
end
config.vm.define "web2" do |web2|
	web2.vm.box = "ubuntu/trusty64"
	web2.vm.network "private_network", ip: "10.0.0.12"
	web2.vm.provision :shell do |shell|
	shell.args = "2"
	shell.path =

"https://gist.githubusercontent.com/abraunton/1bfbf0aba866baa3b1fa/raw/df07f5001ce7296bc6e663f0fd68cbf5c89b9959/provision-web.sh"
  end
end

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end

# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.ssh.forward_agent = false
  config.ssh.pty = false
  config.vm.box_download_insecure = true
  #If you don't have vbguest initially installed or for some reason your installation failed
  #please consider commenting the three lines below "config.vbguest.*"
  config.vbguest.auto_update = false
  config.vbguest.no_remote = true
  config.vbguest.iso_path = "C:/Program Files/Oracle/VirtualBox/VBoxGuestAdditions.iso"
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "ubuntu/xenial64"
  config.disksize.size = '80GB'

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
  config.vm.network "forwarded_port", guest: 80, host: 8080, auto_correct: true
  config.vm.network "forwarded_port", guest: 8000, host: 8090, auto_correct: true
  config.vm.network "forwarded_port", guest: 8001, host: 8091, auto_correct: true
  config.vm.network "forwarded_port", guest: 8002, host: 8092, auto_correct: true
  config.vm.network "forwarded_port", guest: 8080, host: 8093, auto_correct: true
  config.vm.network "forwarded_port", guest: 8081, host: 8094, auto_correct: true
  config.vm.network "forwarded_port", guest: 8082, host: 8095, auto_correct: true
  config.vm.network "forwarded_port", guest: 8091, host: 8096, auto_correct: true
  config.vm.network "forwarded_port", guest: 8092, host: 8097, auto_correct: true
  config.vm.network "forwarded_port", guest: 8093, host: 8098, auto_correct: true
  config.vm.network "forwarded_port", guest: 8094, host: 8099, auto_correct: true
  config.vm.network "forwarded_port", guest: 8095, host: 9000, auto_correct: true
  config.vm.network "forwarded_port", guest: 443, host: 4430, auto_correct: true
  config.vm.network "forwarded_port", guest: 3306, host: 33060, auto_correct: true

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
  config.vm.synced_folder "../code", "/opt/code", :create => true

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  config.vm.provider "virtualbox" do |vb|
    vb.name = "ConsumerPortalBaseVM"
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
	vb.memory = 3072
	vb.cpus = 4
  end
  # exec quod script
  config.vm.provision :shell, path: "bootstrap.sh"
end

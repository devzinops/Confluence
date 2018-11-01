# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"
  config.vm.hostname = "confluence"
  config.vm.box_check_update = false
  #config.ssh.insert_key = false
  #config.vm.network "forwarded_port", guest: 80, host: 8088, host_ip: "127.0.0.1"
  #config.vm.network "private_network", ip: "192.168.56.200"
  config.vm.network "forwarded_port", guest: 8090, host: 8088, host_ip: "127.0.0.1"

  # Configure VM several parameters
    config.vm.provider "virtualbox" do |vb|
      #vb.vm.provision "shell", inline: "echo ubuntu:ubuntu | chpasswd"
      vb.name = "confluence"
       # Display the VirtualBox GUI when booting the machine
      vb.gui = false
       # Customize the amount of memory and CPU on the VM:
      vb.memory = "2048"
      vb.cpus = "2"
    end
  # install python for ansible
  config.vm.provision "shell", inline: "apt-get update && apt-get install -y python-minimal"

  # Run Ansible from the Vagrant Host
    config.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "playbook.yml"
    end

end

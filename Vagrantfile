# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.define "centos1" do |centos1|
    config.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--nicpromisc2", "allow-all"]
      vb.customize ["modifyvm", :id, "--nicpromisc3", "allow-all"]
    end
    centos1.vm.box = "centos/7"
    centos1.vm.hostname = "centos1"
    centos1.ssh.insert_key = false
    centos1.vm.provision "shell",
      inline: "sudo sed -i -e 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config"
    centos1.vm.provision "shell",
      inline: "sudo systemctl restart sshd"
    centos1.vm.network "private_network", type: "dhcp"
    centos1.vm.network "private_network", type: "dhcp"
  end

  config.vm.define "centos2" do |centos2|
    config.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--nicpromisc2", "allow-all"]
      vb.customize ["modifyvm", :id, "--nicpromisc3", "allow-all"]
    end
    centos2.vm.box = "centos/7"
    centos2.vm.hostname = "centos2"
    centos2.ssh.insert_key = false
    centos2.vm.provision "shell",
      inline: "sudo sed -i -e 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config"
    centos2.vm.provision "shell",
      inline: "sudo systemctl restart sshd"
    centos2.vm.network "private_network", type: "dhcp"
    centos2.vm.network "private_network", type: "dhcp"
  end

end

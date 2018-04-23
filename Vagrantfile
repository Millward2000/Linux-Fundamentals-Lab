# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.define "centos1" do |centos7|
    centos7.vm.box = "centos/7"
    centos7.vm.hostname = "centos1"
    config.ssh.insert_key = false
    config.vm.provision "shell",
      inline: "sudo sed -i -e 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config"
    config.vm.provision "shell",
      inline: "sudo systemctl restart sshd"
    config.vm.network "private_network", type: "dhcp"  
  end

  config.vm.define "centos2" do |centos7|
    centos7.vm.box = "centos/7"
    centos7.vm.hostname = "centos2"
    config.ssh.insert_key = false
    config.vm.provision "shell",
      inline: "sudo sed -i -e 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config"
    config.vm.provision "shell",
      inline: "sudo systemctl restart sshd"
    config.vm.network "private_network", type: "dhcp"
  end

end

# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  (1..1).each do |i|
    config.vm.define "ubnt-#{i}" do |ubnt|
      ubnt.vm.box = "ubuntu/focal64"
      ubnt.vm.box_check_update = false
      ubnt.vm.hostname = "ubnt-#{i}"
      ubnt.vm.provision "ansible" do |ansible|
        ansible.playbook = "playbook.yml"
      end
      ubnt.vm.network "public_network", bridge: "en0: Wi-Fi (AirPort)", ip: "192.168.1.12#{i}"
      ubnt.vm.provider "virtualbox" do |vb|
        vb.name = "ubnt-#{i}"
        vb.cpus = 2
        vb.memory = "1024"
      end
    end
  end
  # (1..1).each do |i|
  #   config.vm.define "cnt-#{i}" do |cnt|
  #     cnt.vm.box = "centos/7"
  #     cnt.vm.box_check_update = false
  #     cnt.vm.hostname = "cnt-#{i}"
  #     cnt.vm.network "public_network", bridge: "en0: Wi-Fi (AirPort)", ip: "192.168.1.13#{i}"
  #     cnt.vm.provision "shell", inline: <<-SHELL
  #       yum upgrade -y
  #       timedatectl set-timezone Europe/Moscow
  #       yum install git zsh
  #       yes | sudo sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  #       yes | sudo -u vagrant sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  #       git clone https://github.com/blackden/home_stuff home_stuff
  #       rsync -abvP --chown=root:root ./home_stuff/.{zsh,vim}rc ~root/
  #       rsync -abvP --chown=vagrant:vagrant ./home_stuff/.{zsh,vim}rc ~vagrant/
  #       echo -e "/bin/zsh\n" | chsh
  #       echo -e "/bin/zsh\n" | chsh vagrant
  #       echo "ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIOTqSZyLv/6qXOj3QkhT7Qf1D32m3SyACvwCHbS3A599 MacPro15-ragnar" >> ~vagrant/.ssh/authorized_keys
  #       reboot
  #     SHELL
  #     cnt.vm.provider "virtualbox" do |vb|
  #       vb.name = "cnt-#{i}"
  #       vb.memory = "1024"
  #     end
  #   end
  # end
end

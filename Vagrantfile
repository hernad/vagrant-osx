# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "maverick-osx"
  config.ssh.insert_key = false


  config.vm.synced_folder ".", "/vagrant", type: "rsync",
    rsync__exclude: ".git/",
    rsync__args: ["--verbose", "--rsync-path='rsync'", "--archive", "--delete", "-z"]

  config.vm.provider "virtualbox" do |vb|
     #vb.gui = true
     vb.memory = "2048"
     vb.customize ["modifyvm", :id, "--cpuidset", "1","000206a7","02100800","1fbae3bf","bfebfbff"]
     vb.cpus = 2
  end

  #config.vm.provision "shell", inline: <<-SHELL
  #   echo $PATH
  #   python --version
  #   ruby --version
  #   
  #SHELL
end

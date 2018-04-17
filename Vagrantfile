# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  folder = ENV['SHARED_FOLDER'] || "#{ENV['HOME']}/.ghq"
  config.vm.synced_folder folder, folder
  config.vm.provider "virtualbox" do |vbox|
    vbox.memory = "1024"
    vbox.cpus   = 2
  end

  config.vm.define "control-1" do |ubuntu|
    ubuntu.vm.network "private_network", ip: "192.168.211.1"
  end

  config.vm.define "compute-1" do |ubuntu|
    ubuntu.vm.network "private_network", ip: "192.168.211.11"
    ubuntu.disksize.size = '15GB'
  end
end

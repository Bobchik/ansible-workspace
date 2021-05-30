# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provider :virtualbox do |v|
    v.memory = 256
    v.linked_clone = true
  end

  # Application server1 
  config.vm.define "app1" do |app|
    app.vm.hostname = "orc-app1.test"
    app.vm.network "private_network", ip: "192.168.33.10"
  end

  # Application server2 
  config.vm.define "app2" do |app|
    app.vm.hostname = "orc-app2.test"
    app.vm.network "private_network", ip: "192.168.33.11"
  end

  # Database server
  config.vm.define "db" do |db|
    db.vm.hostname = "orc-db.test"
    db.vm.network "private_network", ip: "192.168.33.12"
  end

  # config.vm.provision "ansible" do |ansible|
  #   ansible.playbook = "playbook.yaml"
  # end
end

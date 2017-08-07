# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.hostname = "django"
  config.vm.network "private_network", ip: "192.168.34.10"
  if ARGV[0] == "up" || ARGV[0] == "provision" then
    config.vm.provision "ansible_local" do |ansible|
      ansible.inventory_path = "./playbook/hosts/local"
      ansible.playbook       = "./playbook/site.yml"
      ansible.limit          = "django"
    end
  end
end

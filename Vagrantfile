# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = 'centos7'
  config.vm.box_url = 'https://github.com/holms/vagrant-centos7-box/releases/download/7.1.1503.001/CentOS-7.1.1503-x86_64-netboot.box'

  config.vm.provider :virtualbox do |vb|
    vb.gui = false
    vb.memory = 1024
    vb.cpus = 1
  end

  if Vagrant.has_plugin?('vagrant-hostsupdater')
    config.hostsupdater.remove_on_suspend = true
  end

  config.vm.hostname = 'randompocket.dev'
  config.vm.network :private_network, ip: '172.17.8.24'

  config.vm.provision :ansible do |ansible|
    ansible.playbook = '../randompocket-ansible-playbook/site.yml'
  end
end

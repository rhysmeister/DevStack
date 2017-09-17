# Vagrantfile to launch a centos 7 box
Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  config.vm.provider :virtualbox do |vb|
    vb.customize [
      "modifyvm", :id,
      "--name", "OpenStack",
      "--memory", "2024"
    ]
  end

  config.vm.hostname = "openstack"
  config.vm.synced_folder '.', '/vagrant', disabled: true
  config.vm.network "private_network", ip: "192.168.4.111"

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "openstack.yaml"
  end

end

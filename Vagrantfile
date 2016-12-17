Vagrant.configure(2) do |config|

  if Vagrant.has_plugin?("vagrant-cachier")
      config.cache.scope = :box
  end

  config.ssh.insert_key = false
  config.vm.provider "virtualbox" do |v|
    v.linked_clone = true
  end

  config.vm.define :centos do |machine|
    machine.vm.box = "centos-7.2"
    machine.vm.box_url = "https://files.studio-moco.net/virtualbox-centos-7.2.1511.box"
    machine.vm.network "private_network", ip: "192.168.33.20"
    machine.vm.provision :shell, inline: "ifup enp0s8", run: "always" # vagrant 1.9.1 issue
    machine.vm.provision :ansible do |ansible|
      ansible.playbook = "tests/site.yml"
      ansible.inventory_path = 'tests/inventory'
      ansible.limit = 'centos'
      ansible.verbose = 'v'
    end
  end

  config.vm.define :ubuntu do |machine|
    machine.vm.box = "ubuntu-16.04"
    machine.vm.box_url = "https://files.studio-moco.net/virtualbox-ubuntu-16.04.box"
    machine.vm.network "private_network", ip: "192.168.33.21"
    machine.vm.provision :ansible do |ansible|
      ansible.playbook = "tests/site.yml"
      ansible.inventory_path = 'tests/inventory'
      ansible.limit = 'ubuntu'
      ansible.verbose = 'v'
    end
  end
end

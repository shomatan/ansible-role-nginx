Vagrant.configure(2) do |config|

  if Vagrant.has_plugin?("vagrant-cachier")
      config.cache.scope = :box
  end

  config.vm.box = "centos-7.2"
  config.vm.provider "virtualbox" do |v|
    v.linked_clone = true
  end

  config.vm.define :default do |machine|
    machine.vm.hostname = "default"
    machine.vm.network :private_network, ip: "192.168.33.20"
    machine.vm.provision :ansible_local do |ansible|
      ansible.playbook = "tests/main.yml"
      ansible.inventory_path = 'inventory'
      ansible.limit = 'all'
      ansible.verbose = 'vv'
      ansible.install = true
    end
  end

end

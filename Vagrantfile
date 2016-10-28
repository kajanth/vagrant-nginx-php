Vagrant.configure("2") do |config|

  config.vm.box_url = "https://vagrantcloud.com/puppetlabs/boxes/ubuntu-14.04-64-nocm"
  config.vm.box = "puppetlabs/ubuntu-14.04-64-nocm"

  config.vm.define "node1" do |machine|
    machine.vm.network "private_network", ip: "172.17.177.21"
  end

  config.vm.define "node2" do |machine|
    machine.vm.network "private_network", ip: "172.17.177.22"
  end

  config.vm.define "node3" do |machine|
    machine.vm.network "private_network", ip: "172.17.177.23"
  end

  config.vm.define "lb" do |machine|
    machine.vm.network "private_network", ip: "172.17.177.24"
  end

  #config.vm.define "db" do |machine|
  #  machine.vm.network "private_network", ip: "172.17.177.25"
  #end

  config.vm.define 'controller' do |machine|
    machine.vm.network "private_network", ip: "172.17.177.11"

    machine.vm.provision :ansible_local do |ansible|
      ansible.playbook       = "playbook.yml"
      ansible.verbose        = true
      ansible.install        = true
      ansible.limit          = "all" # or only "nodes" group, etc.
      ansible.inventory_path = "hosts"
    end
  end

end

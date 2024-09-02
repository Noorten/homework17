Vagrant.configure("2") do |config|
  # Base VM OS
  config.vm.box = "bento/ubuntu-22.04"

  config.vm.provider :virtualbox do |v|
    v.memory = 1512
    v.cpus = 2
  end

  # Two VMs
  boxes = [
    { name: "web", ip: "192.168.56.10" },
    { name: "log", ip: "192.168.56.15" },
    { name: "fulllog", ip: "192.168.56.20" }
  ]

  # Provision
  boxes.each do |opts|
    config.vm.define opts[:name] do |vm_config|
      vm_config.vm.hostname = opts[:name]  
      vm_config.vm.network "private_network", ip: opts[:ip]
    end
  end
end

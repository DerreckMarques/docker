Vagrant.configure("2") do |config|
  
  config.vm.provider "virtualbox" do |v|
        v.memory = 2048
   end

  config.vm.box = "derreckVM/docker"
  config.vm.network "private_network", ip: "192.168.50.4"	
  config.vm.hostname = "docker"
  config.vm.synced_folder "../data", "/vagrant_data"
  
end

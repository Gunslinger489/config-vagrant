Vagrant.configure("2") do |config|
    (1..2).each do |i|
      config.vm.define "node_#{i}" do |node|
            node.vm.box = "hashicorp/bionic64"
            node.vm.network "private_network", ip: "172.16.10.10", auto_config: false 
            node.vm.provision "shell", inline: <<-SHELL
              echo -e "\n --- Updating Packages --- \n"
              sudo apt-get update
              sudo apt-get install -y apache2
            SHELL
        end
    end
  end

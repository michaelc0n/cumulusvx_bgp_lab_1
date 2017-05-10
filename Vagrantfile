Vagrant.configure("2") do |config|

config.vm.define "leaf1" do |leaf1|  
  leaf1.vm.box = "CumulusCommunity/cumulus-vx"
  leaf1.vm.network :private_network, ip: "10.10.1.0/31"
  leaf1.vm.network :private_network, ip: "10.10.2.0/31"
  leaf1.vm.network :private_network, ip: "1.1.1.1/32"
  leaf1.vm.hostname = "leaf1"
  leaf1.vm.network "forwarded_port", guest: 22, host: 2222, id: "ssh", disabled: true
  leaf1.vm.network "forwarded_port", guest: 22, host: 2001
  leaf1.vm.provision "shell", inline: "sed -i 's/zebra=no/zebra=yes/g' /etc/quagga/daemons"
  leaf1.vm.provision "shell", inline: "sed -i 's/bgpd=no/bgpd=yes/g' /etc/quagga/daemons"
  leaf1.vm.provision "shell", inline: "sudo systemctl restart quagga.service"
  leaf1.vm.provision "shell", inline: "sleep 5"
  leaf1.vm.provision "shell", inline: "echo 'router bgp 65101' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf1.vm.provision "shell", inline: "echo 'bgp router-id 1.1.1.1' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf1.vm.provision "shell", inline: "echo 'bgp bestpath as-path multipath-relax' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf1.vm.provision "shell", inline: "echo 'neighbor EBGP peer-group' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf1.vm.provision "shell", inline: "echo 'neighbor EBGP remote-as external' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf1.vm.provision "shell", inline: "echo 'neighbor swp1 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf1.vm.provision "shell", inline: "echo 'neighbor swp2 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf1.vm.provision "shell", inline: "echo 'network 1.1.1.1 mask 255.255.255.255' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf1.vm.provision "shell", inline: "echo 'network 10.10.1.0 mask 255.255.255.254' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf1.vm.provision "shell", inline: "echo 'network 10.10.2.0 mask 255.255.255.254' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf1.vm.provision "shell", inline: "sudo systemctl restart quagga.service"
  
  end
  
config.vm.define "leaf2" do |leaf2|  
  leaf2.vm.box = "CumulusCommunity/cumulus-vx"
  leaf2.vm.network :private_network, ip: "20.20.1.0/31"
  leaf2.vm.network :private_network, ip: "20.20.2.0/31"
  leaf2.vm.network :private_network, ip: "2.2.2.2/32"
  leaf2.vm.hostname = "leaf2"
  leaf2.vm.network "forwarded_port", guest: 22, host: 2222, id: "ssh", disabled: true
  leaf2.vm.network "forwarded_port", guest: 22, host: 2002
  leaf2.vm.provision "shell", inline: "sed -i 's/zebra=no/zebra=yes/g' /etc/quagga/daemons"
  leaf2.vm.provision "shell", inline: "sed -i 's/bgpd=no/bgpd=yes/g' /etc/quagga/daemons"
  leaf2.vm.provision "shell", inline: "sudo systemctl restart quagga.service"
  leaf2.vm.provision "shell", inline: "sleep 5"
  leaf2.vm.provision "shell", inline: "echo 'router bgp 65102' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf2.vm.provision "shell", inline: "echo 'bgp router-id 2.2.2.2' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf2.vm.provision "shell", inline: "echo 'bgp bestpath as-path multipath-relax' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf2.vm.provision "shell", inline: "echo 'neighbor EBGP peer-group' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf2.vm.provision "shell", inline: "echo 'neighbor EBGP remote-as external' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf2.vm.provision "shell", inline: "echo 'neighbor swp1 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf2.vm.provision "shell", inline: "echo 'neighbor swp2 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf2.vm.provision "shell", inline: "echo 'network 2.2.2.2 mask 255.255.255.255' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf2.vm.provision "shell", inline: "echo 'network 20.20.1.0 mask 255.255.255.254' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf2.vm.provision "shell", inline: "echo 'network 20.20.2.0 mask 255.255.255.254' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf2.vm.provision "shell", inline: "sudo systemctl restart quagga.service"
  
  end
  
config.vm.define "leaf3" do |leaf3|  
  leaf3.vm.box = "CumulusCommunity/cumulus-vx"
  leaf3.vm.network :private_network, ip: "30.30.1.0/31"
  leaf3.vm.network :private_network, ip: "30.30.2.0/31"
  leaf3.vm.network :private_network, ip: "3.3.3.3/32"
  leaf3.vm.hostname = "leaf3"
  leaf3.vm.network "forwarded_port", guest: 22, host: 2222, id: "ssh", disabled: true
  leaf3.vm.network "forwarded_port", guest: 22, host: 2003
  leaf3.vm.provision "shell", inline: "sed -i 's/zebra=no/zebra=yes/g' /etc/quagga/daemons"
  leaf3.vm.provision "shell", inline: "sed -i 's/bgpd=no/bgpd=yes/g' /etc/quagga/daemons"
  leaf3.vm.provision "shell", inline: "sudo systemctl restart quagga.service"
  leaf3.vm.provision "shell", inline: "sleep 5"
  leaf3.vm.provision "shell", inline: "echo 'router bgp 65103' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf3.vm.provision "shell", inline: "echo 'bgp router-id 3.3.3.3' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf3.vm.provision "shell", inline: "echo 'bgp bestpath as-path multipath-relax' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf3.vm.provision "shell", inline: "echo 'neighbor EBGP peer-group' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf3.vm.provision "shell", inline: "echo 'neighbor EBGP remote-as external' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf3.vm.provision "shell", inline: "echo 'neighbor swp1 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf3.vm.provision "shell", inline: "echo 'neighbor swp2 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf3.vm.provision "shell", inline: "echo 'network 3.3.3.3 mask 255.255.255.255' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf3.vm.provision "shell", inline: "echo 'network 30.30.1.0 mask 255.255.255.254' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf3.vm.provision "shell", inline: "echo 'network 30.30.2.0 mask 255.255.255.254' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf3.vm.provision "shell", inline: "sudo systemctl restart quagga.service"
  
  end

config.vm.define "leaf4" do |leaf4|  
  leaf4.vm.box = "CumulusCommunity/cumulus-vx"
  leaf4.vm.network :private_network, ip: "40.40.1.0/31"
  leaf4.vm.network :private_network, ip: "40.40.2.0/31"
  leaf4.vm.network :private_network, ip: "4.4.4.4/32"
  leaf4.vm.hostname = "leaf4"
  leaf4.vm.network "forwarded_port", guest: 22, host: 2222, id: "ssh", disabled: true
  leaf4.vm.network "forwarded_port", guest: 22, host: 2004
  leaf4.vm.provision "shell", inline: "sed -i 's/zebra=no/zebra=yes/g' /etc/quagga/daemons"
  leaf4.vm.provision "shell", inline: "sed -i 's/bgpd=no/bgpd=yes/g' /etc/quagga/daemons"
  leaf4.vm.provision "shell", inline: "sudo systemctl restart quagga.service"
  leaf4.vm.provision "shell", inline: "sleep 5"
  leaf4.vm.provision "shell", inline: "echo 'router bgp 65104' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf4.vm.provision "shell", inline: "echo 'bgp router-id 4.4.4.4' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf4.vm.provision "shell", inline: "echo 'bgp bestpath as-path multipath-relax' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf4.vm.provision "shell", inline: "echo 'neighbor EBGP peer-group' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf4.vm.provision "shell", inline: "echo 'neighbor EBGP remote-as external' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf4.vm.provision "shell", inline: "echo 'neighbor swp1 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf4.vm.provision "shell", inline: "echo 'neighbor swp2 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf4.vm.provision "shell", inline: "echo 'network 4.4.4.4 mask 255.255.255.255' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf4.vm.provision "shell", inline: "echo 'network 40.40.1.0 mask 255.255.255.254' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf4.vm.provision "shell", inline: "echo 'network 40.40.2.0 mask 255.255.255.254' |  sudo tee -a /etc/quagga/Quagga.conf"
  leaf4.vm.provision "shell", inline: "sudo systemctl restart quagga.service"
  
  end
  
config.vm.define "spine1" do |spine1|  
  spine1.vm.box = "CumulusCommunity/cumulus-vx"
  spine1.vm.network :private_network, ip: "10.10.1.1/31"
  spine1.vm.network :private_network, ip: "20.20.1.1/31"
  spine1.vm.network :private_network, ip: "30.30.1.1/31"
  spine1.vm.network :private_network, ip: "40.40.1.1/31"
  spine1.vm.network :private_network, ip: "11.11.11.11/32"
  spine1.vm.hostname = "spine1"
  spine1.vm.network "forwarded_port", guest: 22, host: 2222, id: "ssh", disabled: true
  spine1.vm.network "forwarded_port", guest: 22, host: 3001
  spine1.vm.provision "shell", inline: "sed -i 's/zebra=no/zebra=yes/g' /etc/quagga/daemons"
  spine1.vm.provision "shell", inline: "sed -i 's/bgpd=no/bgpd=yes/g' /etc/quagga/daemons"
  spine1.vm.provision "shell", inline: "sudo systemctl restart quagga.service"
  spine1.vm.provision "shell", inline: "sleep 5"
  spine1.vm.provision "shell", inline: "echo 'router bgp 65500' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine1.vm.provision "shell", inline: "echo 'bgp router-id 11.11.11.11' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine1.vm.provision "shell", inline: "echo 'bgp bestpath as-path multipath-relax' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine1.vm.provision "shell", inline: "echo 'neighbor EBGP peer-group' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine1.vm.provision "shell", inline: "echo 'neighbor EBGP remote-as external' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine1.vm.provision "shell", inline: "echo 'neighbor swp1 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine1.vm.provision "shell", inline: "echo 'neighbor swp2 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine1.vm.provision "shell", inline: "echo 'neighbor swp3 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine1.vm.provision "shell", inline: "echo 'neighbor swp4 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine1.vm.provision "shell", inline: "echo 'network 11.11.11.11 mask 255.255.255.255' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine1.vm.provision "shell", inline: "sudo systemctl restart quagga.service"
  
  end

config.vm.define "spine2" do |spine2|  
  spine2.vm.box = "CumulusCommunity/cumulus-vx"
  spine2.vm.network :private_network, ip: "10.10.2.1/31"
  spine2.vm.network :private_network, ip: "20.20.2.1/31"
  spine2.vm.network :private_network, ip: "30.30.2.1/31"
  spine2.vm.network :private_network, ip: "40.40.2.1/31"
  spine2.vm.network :private_network, ip: "22.22.22.22/32"
  spine2.vm.hostname = "spine2"
  spine2.vm.network "forwarded_port", guest: 22, host: 2222, id: "ssh", disabled: true
  spine2.vm.network "forwarded_port", guest: 22, host: 3002
  spine2.vm.provision "shell", inline: "sed -i 's/zebra=no/zebra=yes/g' /etc/quagga/daemons"
  spine2.vm.provision "shell", inline: "sed -i 's/bgpd=no/bgpd=yes/g' /etc/quagga/daemons"
  spine2.vm.provision "shell", inline: "sudo systemctl restart quagga.service"
  spine2.vm.provision "shell", inline: "sleep 5"
  spine2.vm.provision "shell", inline: "echo 'router bgp 65500' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine2.vm.provision "shell", inline: "echo 'bgp router-id 22.22.22.22' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine2.vm.provision "shell", inline: "echo 'bgp bestpath as-path multipath-relax' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine2.vm.provision "shell", inline: "echo 'neighbor EBGP peer-group' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine2.vm.provision "shell", inline: "echo 'neighbor EBGP remote-as external' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine2.vm.provision "shell", inline: "echo 'neighbor swp1 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine2.vm.provision "shell", inline: "echo 'neighbor swp2 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine2.vm.provision "shell", inline: "echo 'neighbor swp3 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine2.vm.provision "shell", inline: "echo 'neighbor swp4 interface peer-group EBGP' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine2.vm.provision "shell", inline: "echo 'network 22.22.22.22 mask 255.255.255.255' |  sudo tee -a /etc/quagga/Quagga.conf"
  spine2.vm.provision "shell", inline: "sudo systemctl restart quagga.service"
	
  end

end  

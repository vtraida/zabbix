Vagrant.configure("2") do |config|
config.vm.box = "centos/7"
HOST_HOSTNAME= `hostname`.strip
#zabbix server
config.vm.define "srv-zab" do |srv|
#srv.config.vm.box = "centos/7"
srv.vm.hostname = "srvzab.test"
srv.vm.network :private_network, ip: "192.168.61.101"
srv.vm.network :"public_network" , bridge: [
  "enp0s31f6",
  "wlp2s0",
  "en0: Wi-Fi (AirPort)"
]
srv.vm.network "forwarded_port", guest: 80, host:8011
srv.vm.provider :virtualbox do |vbox|
  vbox.name = "srvzab"
  vbox.memory = 1024
  end
 end

#test vm

config.vm.define "srv-zab01" do |srv1|
#srv1.config.vm.box = "centos/7"
srv1.vm.hostname = "#{HOST_HOSTNAME}t#{rand(20..99)}"+".kyiv.epam.com"
srv1.vm.network :private_network, ip: "192.168.61.102"
srv1.vm.network :"public_network" , bridge: [
  "enp0s31f6",
  "wlp2s0",
  "en0: Wi-Fi (AirPort)"
]
srv1.vm.network "forwarded_port", guest: 80, host:8010
srv1.vm.provider :virtualbox do |vbox|
  vbox.name = "srvzab01"
  vbox.memory = 1024
  end
 end


config.vm.provision "shell", inline: "echo Hello"

#config.vm.provision :shell, path: "install_stuff.sh"
#config.vm.provision "ansible" do |ansible|
# ansible.playbook = "jenkins_install.yml

end
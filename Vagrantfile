Vagrant.configure("2") do |config|
config.vm.box = "centos/7"

#zabbix server
config.vm.define "srv-zab" do |srv|
#srv.config.vm.box = "centos/7"
srv.vm.hostname = "srvzab.test"
srv.vm.network :private_network, ip: "192.168.61.101"
srv.vm.network :"public_network" , bridge: [
  "enp0s31f6",
  "wlp2s0",
]
srv.vm.network "forwarded_port", guest: 80, host:8010
srv.vm.provider :virtualbox do |vbox|
  vbox.name = "srvzab"
  end
 end


config.vm.provision "shell", inline: "echo Hello"

config.vm.provision :shell, path: "install_stuff.sh"
#config.vm.provision "ansible" do |ansible|
# ansible.playbook = "jenkins_install.yml

end
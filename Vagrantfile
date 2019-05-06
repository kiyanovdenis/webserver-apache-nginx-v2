
# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"
  config.vm.synced_folder ".", "/vagrant", type: "virtualbox"
  config.vm.network "public_network", bridge: "enp3s0", ip: "192.168.13.1"
  config.vm.network "public_network", bridge: "enp3s0", ip: "192.168.13.2"
  config.vm.define 'webserver' do |node|
   node.vm.hostname = 'webserver.local'
   node.vm.provision "ansible" do |ansible|
    ansible.playbook = "main.yml"
   end
  end
end

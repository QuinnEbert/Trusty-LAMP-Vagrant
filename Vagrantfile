VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.provision "shell",
      inline: "apt-get -y update && apt-get -y upgrade && debconf-set-selections <<< 'mysql-server mysql-server/root_password password password' && debconf-set-selections <<< 'mysql-server mysql-server/root_password_again password password' && apt-get -y install lamp-server^"
  config.vm.network "public_network", bridge: 'en0: Ethernet'
   config.vm.provider "virtualbox" do |vb|
     vb.customize ["modifyvm", :id, "--memory", "800"]
   end
end

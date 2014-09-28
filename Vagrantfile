# -*- mode: ruby -*-
# vi: set ft=ruby :
VAGRANTFILE_API_VERSION = "2"
$script = <<-SCRIPT
apt-get update
apt-get install -y apache2 curl
a2enmod cgid
service apache2 restart
cp /vagrant/shellshock.cgi /usr/lib/cgi-bin/
chmod +x /usr/lib/cgi-bin/shellshock.cgi
SCRIPT

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "hashicorp/precise32"
  config.vm.provision "shell", inline: $script
end

vm_name = "Debian GNU Linux 11 (bullseye)"
vm_host_name = "devexapleinc"
vm_script_name = "VMScript.sh"
vm_image = "debian/bullseye64"

Vagrant.configure("2") do | config |
	config.vm.box = vm_image
	config.vm.hostname = vm_host_name
	config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"	
	config.vm.define vm_name
	config.vm.synced_folder "./site/", "/var/www/html/",owner: "www-data", group: "www-data"
	config.vm.provider "virtualbox" do | vb | vb.name = vm_name; vb.gui = true; end
	config.vm.provision "shell", path: vm_script_name
end

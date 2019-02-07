Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/xenial64"
	config.vm.network "private_network", ip: "10.4.4.52"
	config.vm.network "forwarded_port", guest: 80, host: 8080
	config.vm.network "forwarded_port", guest: 3306,  host: 33306
    config.vm.synced_folder "phalcon", "/var/www/phalcon",
        type: "virtualbox",
        create: true,
        id: "vagrant-root",
        owner: "vagrant",
        group: "www-data",
        mount_options: ["dmode=775,fmode=775"]
    config.vm.provision "shell", path: "bootstrap.sh", privileged: false
end

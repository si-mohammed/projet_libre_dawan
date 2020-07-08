# -*- mode: ruby -*-
# vi: set ft=ruby :
# variable d'environnement 
  # varibale répertoir du backEnd
    FrontEnd_path = "/mnt/mes-sites/Mon_site"
     # path des data pour le serveur apache
    VM_FrontEnd_path = "/vagrant_data"
    BackEnd_path = "/mnt/mes-sites/Mon_site"
    # path des data pour le serveur apache
    VM_BackEnd_path = "/var/www/html"

    BD_noSQL_path = "/mnt/mes-sites/Mon_site"
     # path des data pour le serveur postgresql
     VM_BD_noSQL_path = "/vagrant_data"
    BD_MySQL_path = "/mnt/mes-sites/Mon_site"
     # path des data pour le serveur MySQL
     VM_BD_MySQL_path = "/vagrant_data"
    Host_bridge = "enp3s0"
    


# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
# The most common configuration options are documented and commented below.
# For a complete reference, please see the online documentation at
# https://docs.vagrantup.com.

# Every Vagrant development environment requires a box. You can search for
# boxes at https://vagrantcloud.com/search.

config.vm.provision "shell",
    inline: <<-F00
               echo "Hello, World, Mohammed infra pour mon site"
            F00
          
  # config pour la VM FrontEnd
config.vm.define "frontEnd", primary: true do |frontEnd|
      frontEnd.vm.box = "ubuntu/trusty64"
      # Disable automatic box update checking. If you disable this, then
      # boxes will only be checked for updates when the user runs
      # `vagrant box outdated`. This is not recommended.
      config.vm.box_check_update = true
      frontEnd.vm.provision "shell",
        inline: <<-F00
               echo "Hello, World, Mohammed frontEnd"
            F00
      #FrontEnd.vm.provision "shell",    
      #        inline: <<-FFontEnd
      #               sudo apt update
      #               sudo apt install -y Nginx
      #            FFrontEnd



     # Create a forwarded port mapping which allows access to a specific port
     # within the machine from a port on the host machine. In the example below,
     # accessing "localhost:8080" will access port 80 on the guest machine.
     # NOTE: This will enable public access to the opened port
     #config.vm.network "forwarded_port", guest: 81, host: 8081

     # Create a forwarded port mapping which allows access to a specific port
     # within the machine from a port on the host machine and only allow access
     # via 127.0.0.1 to disable public access
     #config.vm.network "forwarded_port", guest: 81, host: 8081, host_ip: "127.0.0.1"

     # Create a private network, which allows host-only access to the machine
     # using a specific IP.
     config.vm.network "private_network", type: "dhcp",  bridge: Host_bridge
     # Create a public network, which generally matched to bridged network.
     # Bridged networks make the machine appear as another physical device on
     # your network.
     config.vm.network "public_network", bridge: Host_bridge
   
     # Share an additional folder to the guest VM. The first argument is
     # the path on the host to the actual folder. The second argument is
     # the path on the guest to mount the folder. And the optional third
     # argument is a set of non-required options.
     config.vm.synced_folder FrontEnd_path, VM_FrontEnd_path

     # Provider-specific configuration so you can fine-tune various
     # backing providers for Vagrant. These expose provider-specific options.
     # Example for VirtualBox:
     #
     config.vm.provider "virtualbox" do |vb|
     #   # Display the VirtualBox GUI when booting the machine
       vb.gui = true
  
     # Configuration du nom de la VM
     vb.name = "server_FrontEnd  Nginx"

     #   # Customize the amount of memory on the VM:
     vb.memory = "1024"
     end
     
end

###############################################################################################
# Partie BackEnd

  
          
  # config pour la VM BackEnd
config.vm.define "backEnd", primary: true do |backEnd|
      backEnd.vm.box = "ubuntu/trusty64"
      # Disable automatic box update checking. If you disable this, then
      # boxes will only be checked for updates when the user runs
      # `vagrant box outdated`. This is not recommended.
      config.vm.box_check_update = true
      
      backEnd.vm.provision "shell",
        inline: <<-F00
               echo "Hello, World, Mohammed backEnd"
            F00
      #FrontEnd.vm.provision "shell",    
      #        inline: <<-FbackEnd
      #               sudo apt update
      #               sudo apt install -y apache2
      #            FbackEnd



      # Create a forwarded port mapping which allows access to a specific port
      # within the machine from a port on the host machine. In the example below,
      # accessing "localhost:8080" will access port 80 on the guest machine.
      # NOTE: This will enable public access to the opened port
      #config.vm.network "forwarded_port", guest: 82, host: 8082

      # Create a forwarded port mapping which allows access to a specific port
      # within the machine from a port on the host machine and only allow access
      # via 127.0.0.1 to disable public access
      #config.vm.network "forwarded_port", guest: 82, host: 8082, host_ip: "127.0.0.1"

      # Create a private network, which allows host-only access to the machine
      # using a specific IP.
      config.vm.network "private_network", type: "dhcp",  bridge: Host_bridge

      # Create a public network, which generally matched to bridged network.
      # Bridged networks make the machine appear as another physical device on
      # your network.
      #config.vm.network "public_network"
   
      # Share an additional folder to the guest VM. The first argument is
      # the path on the host to the actual folder. The second argument is
      # the path on the guest to mount the folder. And the optional third
      # argument is a set of non-required options.
      config.vm.synced_folder BackEnd_path, VM_BackEnd_path

      # Provider-specific configuration so you can fine-tune various
      # backing providers for Vagrant. These expose provider-specific options.
      # Example for VirtualBox:
      #
      config.vm.provider "virtualbox" do |vb|
      #   # Display the VirtualBox GUI when booting the machine
        vb.gui = true
  
      # Configuration du nom de la VM
        vb.name = "server_BackEnd  apache2"

      #   # Customize the amount of memory on the VM:
        vb.memory = "1024"
      end
    
end




 ############################################################################################  
# Partie BD_noSQL


          
  # config pour la VM BD_noSQL
config.vm.define "bd_noSQL", primary: true do |bd_noSQL|
      
      config.vm.provision "shell",
        inline: <<-F00
               echo "Hello, World, Mohammed BD_noSQL"
            F00
      bd_noSQL.vm.box = "ubuntu/trusty64"
      # Disable automatic box update checking. If you disable this, then
      # boxes will only be checked for updates when the user runs
      # `vagrant box outdated`. This is not recommended.
      config.vm.box_check_update = true

      #BD_noSQL.vm.provision "shell",    
      #        inline: <<-Fbd_noSQL
      #               sudo apt update
      #               sudo apt install -y postgresql postgresql-contrib
      #            Fbd_noSQL



     # Create a forwarded port mapping which allows access to a specific port
     # within the machine from a port on the host machine. In the example below,
     # accessing "localhost:8080" will access port 80 on the guest machine.
     # NOTE: This will enable public access to the opened port
     #config.vm.network "forwarded_port", guest: 83, host: 8083

     # Create a forwarded port mapping which allows access to a specific port
     # within the machine from a port on the host machine and only allow access
     # via 127.0.0.1 to disable public access
     #config.vm.network "forwarded_port", guest: 83, host: 8083, host_ip: "127.0.0.1"

     # Create a private network, which allows host-only access to the machine
     # using a specific IP.
     config.vm.network "private_network", type: "dhcp",  bridge: Host_bridge

     # Create a public network, which generally matched to bridged network.
     # Bridged networks make the machine appear as another physical device on
     # your network.
     # config.vm.network "public_network"
   
     # Share an additional folder to the guest VM. The first argument is
     # the path on the host to the actual folder. The second argument is
     # the path on the guest to mount the folder. And the optional third
     # argument is a set of non-required options.
     config.vm.synced_folder BD_noSQL_path, VM_BD_noSQL_path

     # Provider-specific configuration so you can fine-tune various
     # backing providers for Vagrant. These expose provider-specific options.
     # Example for VirtualBox:
     #
     config.vm.provider "virtualbox" do |vb|
     #   # Display the VirtualBox GUI when booting the machine
       vb.gui = true
  
     # Configuration du nom de la VM
     vb.name = "server_BD NoSQL  postgresql"

     #   # Customize the amount of memory on the VM:
     vb.memory = "1024"
     end
     
end



 ############################################################################################  
# Partie BD_MySQL
config.vm.provision "shell",
    inline: <<-F00
               echo "Hello, World, Mohammed BD_MySQL"
            F00


config.vm.define "db_MySQL" do |db_MySQL|
    db_MySQL.vm.box = "ubuntu/trusty64"

    config.vm.box_check_update = true

    #db_MySQL.vm.provision "shell",
     #  inline: <<-Fdb_MySQL
     #         sudo apt update
     #           sudo apt install -y mariadb-server
     #         Fdb_MySQL


    #config.vm.network "forwarded_port", guest: 84, host: 8084
    config.vm.network "private_network", type: "dhcp",  bridge: Host_bridge
    #config.ssh.dsa_authentication = false
    #db_MySQL.vm.network "forwarded_port", guest: 84, host: 8084, host_ip: "127.0.0.1"


     # Share an additional folder to the guest VM. The first argument is
     # the path on the host to the actual folder. The second argument is
     # the path on the guest to mount the folder. And the optional third
     # argument is a set of non-required options.
    config.vm.synced_folder BD_MySQL_path, VM_BD_MySQL_path


    db_MySQL.vm.provider "virtualbox" do |vb|
#   # Display the VirtualBox GUI when booting the machine
      vb.gui = true
    #
# Configuration du nom de la VM
      vb.name = "server_mariadb"
#   # Customize the amount of memory on the VM:
      vb.memory = "2048"
    end
end

end

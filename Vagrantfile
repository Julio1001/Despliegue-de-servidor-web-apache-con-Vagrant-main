# Vagrantfile para crear un servidor Apache
Vagrant.configure("2") do |config|
    # Usar una caja base de Ubuntu
    config.vm.box = "ubuntu/bionic64"
  
    # Configuración de la máquina virtual
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"  # RAM
      vb.cpus = 1        # CPU
    end
  
    # Configuración de red
    config.vm.network "forwarded_port", guest: 80, host: 8080
  
    # Compartir directorio local con el directorio de Apache en la VM
    config.vm.synced_folder "./html", "/var/www/html"
  
    # Comandos para instalar y activar Apache
    config.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
    SHELL
  end
  
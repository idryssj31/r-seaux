# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Configuration commune à toutes les machines
  config.vm.box = "b2-tp2-centos.box"
 

  # Config une première VM "node1"
  config.vm.define "node1" do |node1|
    # remarquez l'utilisation de 'node1.' défini sur la ligne au dessus
    node1.vm.network "private_network", ip: "192.168.2.21"
    node1.vm.hostname = "node1.tp2.b2"

      node1.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.name = node1
      end
  end

  # Config une deuxieme VM "node2"
  config.vm.define "node2" do |node2|
    # remarquez l'utilisation de 'node2.' défini sur la ligne au dessus
    node2.vm.network "private_network", ip: "192.168.2.22"
    node2.vm.hostname = "node2.tp2.b2"
    
      node2.vm.provider "virtualbox" do |v|
      v.memory = 512
      v.name = node2
      end
  end

  ## Les 3 lignes suivantes permettent d'éviter certains bugs et/ou d'accélérer le déploiement. Gardez-les tout le temps sauf contre-indications.
  # Ajoutez cette ligne afin d'accélérer le démarrage de la VM (si une erreur 'vbguest' est levée, voir la note un peu plus bas)
  config.vbguest.auto_update = false
  # Désactive les updates auto qui peuvent ralentir le lancement de la machine
  config.vm.box_check_update = false 
  # La ligne suivante permet de désactiver le montage d'un dossier partagé (ne marche pas tout le temps directement suivant vos OS, versions d'OS, etc.)
  config.vm.synced_folder ".", "/vagrant", disabled: true
end






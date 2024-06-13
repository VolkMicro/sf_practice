# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Устанавливаем базовый образ Ubuntu 18.04
  config.vm.box = "bento/ubuntu-18.04"

  # Настраиваем синхронизированную папку
  config.vm.synced_folder ".", "/vagrant", type: "virtualbox"

  # Выполняем сценарий для установки необходимых пакетов
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y python3 python3-pip libpq-dev
    pip3 install psycopg2-binary django
  SHELL

  # Копируем пустой файл на виртуальную машину
  config.vm.provision "file", source: "./my_empty_file.txt", destination: "/home/vagrant/my_empty_file.txt"
end

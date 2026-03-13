# PXEHW
Домашнее задание на тему: "PXE сервер"
Задание:
Что нужно сделать?
Настроить загрузку по сети дистрибутива Ubuntu 24
Установка должна проходить из HTTP-репозитория.
Настроить автоматическую установку c помощью файла user-data
Задания со звёздочкой*
Настроить автоматическую загрузку по сети дистрибутива Ubuntu 24 c использованием UEFI
Для начала как обычно устанавливаем Vagrant, VirtualBox и Ansible:
Установка Vagrant:
wget -O - https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(grep -oP '(?<=UBUNTU_CODENAME=).*' /etc/os-release || lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
apt update && sudo apt install vagrant
Установка VirtualBox:
apt install virtualbox
Установка Ansible:
apt install software-properties-common
add-apt-repository --yes --update ppa:ansible/ansible
apt install ansible
Создаём диреторию, пишем нужные нам файлы и поднимаем нашу машину:
vagrant up
Если ОС поднялась, а плебук выполнился, то задание выполнено!
После успешной загрузки ISO провижининг завершится, и вы сможете перезагрузить клиента для чистой PXE-установки.

CONFLUENCE ON LOCAL MAСHINE

Install Confluence on Virtual Maсhine using Vagrant and Ansible

For Confluence I create VM using Vagrant with parameters: ubuntu/xenial64, 2 Gb memory, 2 Core CPU.
The installation proccess takes place using Vagrant Ansible provisioner and lasts about ten minutes.
At the and of the proccess you need open link in your browser http://localhost:8088 and begin the setup process.

If you want to use my project you need change passwords on file
roles/install_mysql/vars/main.yml

# myproject
this was a project created in Devops lab on 05/04/2025



1.wsl --install 2.sudo apt update 3.sudo apt install ansible -y 4.ansible --version. 5.mkdir ~/ansible-lab. 6.cd ~/ansible-lab. 7.nano hosts.
In the editor, type the following: [local] localhost ansible_connection=local

in cmd: ansible -i hosts local -m ping

Create a new YAML file: nano install_nginx.yml

Add the following content: -name: Install and start NGINX on localhost hosts: local become: yes

tasks name: Install NGINX apt name: nginx state: present update cache: yes

name. Ensure NGINX is running service name: nginx state: started enabled: yes Save and exit (CTRL+O, Enter, then CTRL+X)

Executing the Playbook To run the playbook, use the following command:

ansible-playbook -i hosts install_nginx.yml This command will install Nginx on your localhost. You may see output indicating the status of the installation, including any skipped or failed tasks.

Verifying the Installation To verify that Nginx is running, open your web browser and navigate to:

curl http://localhost

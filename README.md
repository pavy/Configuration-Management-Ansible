# HW1
Ansible Homework

Screencast link - https://youtu.be/krItVOf1qqw

Following is the folder structure I have uploaded -
|
|- boxes
|    |----ansible
|    |----AppServer
|    |----TestServer
|-scripts
     |----templates
     |----main.yml
     |---- Playbooks
     
 Vagrant files are present in boxes directory and scripts has all the playbooks.
 
To provision, clone this repository and give the location of your scripts folder inside "boxes/ansible/Vagrantfile" as source folder to sync directories inside VM. 

Set up the 3 servers using - 
vagrant up

Execute vagrant ssh-config to get private key of the App and Test server and place it inside ansible server under keys directory.

In the ansible VM, from the scripts folder run - ansible-playbook main.yml -i inventory -s

Once the script ends it's execution, run the following commands on App server- 
cd ~/Project/CoffeeMaker
mvn spring-boot:run 

Application is accesible at 192.168.33.100:8080.

You can test the application by running the following commands on Test server - 
cd ~/Project/src
sudo mvn test

You will see 3 passing test cases and BUILD SUCCESSFUL.
 

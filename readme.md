As a developer we always encounter enviroment issue, sometimes we just want to test a framework e.g: we want to try a new version Spring Data for MongoDB, we have to setup MongoDB enviroment. If we can't install MongoDB smoothly that really impact our passion.
============================
This project is mainly for help developer to setup a enviroment based on <a href="https://www.vagrantup.com/">Vagrant</a> + <a href="http://www.ansible.com/home">Ansible</a>.
----------------------------------
Vagrant:
--------------------------------------------------------	
	Description:
	We have three VMs : db, app, web
	* db - to handle database relevant enviroment such as: postgresql, mongodb
	* app - to handle applicatioin server such as: tomcat, nodejs, gunicorn
	* web - to handle http server such as: nginx
	Instruction:
		Start all VM
		cd vagrant
		vagrant up
		Start db VM
		vagrant up db	
		Start app VM
		vagrant up app
		Start web VM
		vagrant up web	

Ansible:
----------------------------------

	To provide particular playbook to install software.
	[DB] - Keep db VM is running.
		[Postgresql]
		cd playbooks
		ansible-playbook db/postgresql.yml
		test your postgresql enviroment:
		psql -h localhost -U postgres --password
		test from Vagrant VM
		cd vagrant
		vagrant ssh db
		sudo su
		sudo -U postgres psql -l

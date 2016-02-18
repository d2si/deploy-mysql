# Ansible Role: MySQL


Installs and configures MySQL Debian/Ubuntu servers.

## Requirements

None.

## Role Variables

Important Variables are:

	mysql_first_deploy: False|True => enable/disable replication master to master
	mysql_replication_role: master-master|master|slave
	mysql_replication_master: "master-host-ip"

In case of multimasters replication, you have to run twice the deploy.yaml:

The first with:
	
	mysql_first_deploy: True 

to deploy **master/slave** configuration

The	Second with:

	mysql_first_deploy: False

to enable **auto-replication** process with **master_log_file** and **master_log_position**
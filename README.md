# MySQL multi-master-slave deployment on Debian

## Ansible Role: mysql

Installs and configures MySQL on Debian servers.

### Requirements

None.

### Role Variables

Important Variables are:

	mysql_replication_role: master-master|master|slave
	mysql_replication_master: "master-host-ip"

## Ansible Role: keepalived

Installs and configures keepalived on Debian servers.

### Requirements

None.

### Role Variables

Important Variables are:

        XXXTODO: ipsum

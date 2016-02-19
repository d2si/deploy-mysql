# MySQL multi-master-slave deployment on Debian with Ansible

## Role: mysql

Installs and configures MySQL on Debian servers.

### Most important variables

    mysql_replication_role: master-master|master|slave
    mysql_replication_master: "master-host-ip"
    mysql_cfg_override: ""

### Few example variables

    mysql_user_home: /root
    mysql_root_username: root
    mysql_root_password: root
    mysql_root_password_update: no
    mysql_datadir: /var/lib/mysql
    mysql_replication_user: []

## Role: keepalived

Installs and configures keepalived on Debian servers.

### Most important variables

    keepalived_vrrp_instances: VRRP instance block
    keepalived_vrrp_instances.key: name of the VRRP instance
    keepalived_vrrp_instances.key.interface: interface bound by VRRP
    keepalived_vrrp_instances.key.state: MASTER|BACKUP
    keepalived_vrrp_instances.key.priority: for electing MASTER highest priority
    keepalived_vrrp_instances.key.virtual_router_id: instance ID of VRRPD
    keepalived_vrrp_instances.key.authentication: authentication block
    keepalived_vrrp_instances.key.authentication.auth_type: PASS|AH
    keepalived_vrrp_instances.key.authentication.auth_pass: password
    keepalived_vrrp_instances.key.virtual_ipaddresses: VRRP IP address block

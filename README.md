# MySQL multi-master-slave deployment on Debian with Ansible

## Role: mysql

Installs and configures MySQL on Debian servers.

### Requirements

None.

### Most important variables

    mysql_replication_role: master-master|master|slave
    mysql_replication_master: "master-host-ip"

### Few example variables

    mysql_user_home: /root

The home directory inside which Python MySQL settings will be stored, which Ansible will use when connecting to MySQL. This should be the home directory of the user which runs this Ansible role.

    mysql_root_password: root

The MySQL root user account password.

    mysql_root_password_update: no

Whether to force update the MySQL root user's password. By default, this role will only change the root user's password when MySQL is first configured. You can force an update by setting this to `yes`.

    mysql_enabled_on_startup: yes

Whether MySQL should be enabled on startup.

    mysql_port: "3306"
    mysql_bind_address: '0.0.0.0'
    mysql_datadir: /var/lib/mysql
    mysql_tmpdir: /tmp

Default MySQL connection configuration.

    mysql_slow_query_log_enabled: no
    mysql_slow_query_log_file: /var/log/mysql-slow.log
    mysql_slow_query_time: 2

Slow query log settings.

    mysql_server_id: "1"
    mysql_max_binlog_size: "100M"
    mysql_expire_logs_days: "10"
    mysql_replication_role: ''
    mysql_replication_master: ''
    mysql_replication_user: []

Replication settings.

## Role: keepalived

Installs and configures keepalived on Debian servers.

### Requirements

None.

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

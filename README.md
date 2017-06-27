# Ansible Role: Zabbix-server

Installs zabbix-server and agent for RedHat/CentOS(6) and Ubuntu linux server.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values:

    # The defaults provided by this role are specific to each distribution
       mysql_root_password: "root@123"
       zabbix_db_password: "password"
       zabbix_server_ip: "192.168.33.52"
       zabbix_db_name: "zabbixdb"
       zabbix_db_user_name: "zabbix"

Set these defaults according to your infrastructure.


## Dependencies

None.

## Example Playbook (installs zabbix-server version 3.0 and above)

    - hosts: zabbix
      roles:
        - zabbix

## Example Playbook (install zabbix-server and agent)

For RHEL / CentOS:

    - hosts: zabbix
      roles:
        - role: zabbix
          when: "ansible_os_family == 'RedHat'"
          mysql_root_password:
            - root
          zabbix_db_password: 
            - password
          zabbix_server_ip: 
            - 192.168.33.52
          zabbix_db_name: 
            - zabbixdb
          zabbix_db_user_name: 
            - zabbix

## License

MIT / BSD

## Author Information

www.opstree.com

blog.opstree.com

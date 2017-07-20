# Ansible Role: Zabbix-server

Installs zabbix-server and client for Ubuntu Xenial.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values:

    # The defaults provided by this role are specific to each distribution
       mysql_root_password: "root@123"
       zabbix_database_password: "zabbix"
       zabbix_server_ip: "localhost"
       version_name: "xenial"


Set the mysql_root_passowrd accordingly. version name is given as a variable for future developement. Leave it as default


## Dependencies

None.

## Example Playbook (installs default zabbix-server available)

    - hosts: zabbix-server
      roles:
        - zabbix

## Example Playbook (install zabbix-server client)

For Xenial Ubuntu:

    - hosts: zabbix-server
      roles:
        - role: zabbix
          when: "ansible_os_family == 'Debian'"
          mysql_root_password:
            - root
          zabbix_database_password
            - zabbix
          zabbix_server_ip:
            - localhost
          version_name:
            - xenial

## License

MIT / BSD

## Author Information

www.opstree.com

blog.opstree.com

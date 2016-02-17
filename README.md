Role Name
=========

Fail2ban basic install and configuration

Requirements
------------

Role Variables
--------------

- **fail2ban_service_enabled**: yes/no start on boot
- **fail2ban_service_state**: started/stopped service status after execution of role

- **fail2ban_jail**:
  ssh:
    enabled: true
    port: ssh
    filter: sshd
    logpath: /var/log/auth.log
    maxretry: 6
  ssh-ddos:
    enabled: true
    port: ssh
    filter: sshd-ddos
    logpath: /var/log/auth.log
    maxretry: 6

- **fail2ban_jail_template**: jail.local template to install, relative to the ansible repository root

- **fail2ban_ignoreip**: (Update this list at your own risk !)
- **fail2ban_ignoreip_extra**: "fail2ban_ignoreip_extra" can be an IP address, a CIDR mask or a DNS host. 
                          Fail2ban will not ban a host which matches an address in this list. Several addresses can be defined using space separator.

- **fail2ban_bantime**: the number of seconds that a host is banned.

### A host is banned if it has generated "maxretry" during the last "findtime"

- **fail2ban_findtime**
- **fail2ban_maxretry**

Dependencies
------------

License
-------


Author Information
------------------

STEAMULO - http://www.steamulo.com
# Ansible Role: haproxy
=========

A simple Ansible role for installing and configuring haproxy for RHEL/CentOS 7 and Debian 10 from repository.

- Install the necessary packages;
- Create configuration file;


Requirements
------------

- The SELinux and firewall settings are not considered to be a concern of this role.

Role Variables
--------------


Variables below are required

| Variable                                     | Default                       | Comments                                     
| :---                                         | :---                          | :---       
|                                              |                               |
| `haproxy_chroot`                             | /var/lib/haproxy              |
|                                              |                               |
| `haproxy_pidfile`                            | /var/run/haproxy.pid          |
|                                              |                               |
| `haproxy_socket`                             | var/lib/haproxy/stats         |
|                                              |                               |
| `haproxy_user`                               | haproxy                       |
|                                              |                               |
| `haproxy_group`                              | haproxy                       |
|                                              |                               |
| `haproxy_ssl`                                |                               | SSL Configuration
|                                              |                               |
| `haproxy_defaults`                           |                               | Defaults Configurations. Change parameters to meet your needs
|                                              |                               |
| `haproxy_bind_address`                       | *                             | Inform IP address ou use default
|                                              |                               |
| `haproxy_frontend_mode`                      | http                          |
|                                              |                               |
| `haproxy_frontend_https_name`                |                               | Inform frontend name
|                                              |                               |
| `haproxy_frontend_ssl_port`                  | 443                           | SSL port
|                                              |                               |
| `haproxy_backend_name`                       |                               | Inform backend name
|                                              |                               |
| `haproxy_balance`                            | roundrobin                    | Enter the type of balancing algorithm
|                                              |                               |
| `haproxy_backend_servers`                    |                               | Web Servers
|                                              |                               |
| `name`                                       |                               | Web server name
|                                              |                               |
| `address`                                    |                               | Web server IP address
|                                              |                               |
| `haproxy_pem_file`                           |                               | PEM file
|                                              |                               |
| `haproxy_crt_file`                           |                               | CRT file
|                                              |                               |
| `haproxy_key_file`                           |                               | KEY file
|                                              |                               |
 

Dependencies
------------

You need to install python-apt package on debian 10 

Installing certificates
-----------------------

E.g. you have a server key example.com.key and certificate file example.com.key. The directory structure should look:

.
└── files

    ├── example.com.crt
    
    └── example.com.key
    
    |__ example.com.pem


Example Playbook
----------------

---
- hosts: haproxy_server

  roles:

    - /path/haproxy

...

## Contributing

Issues, feature requests, ideas are appreciated and can be posted in the Issues section.


Author Information
------------------
LinkedIn: https://br.linkedin.com/in/almircandido

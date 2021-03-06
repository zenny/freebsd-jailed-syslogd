freebsd-jailed-syslogd
======================

This role provides a jailed syslogd server. Nothing more.

To see this role in action, have a look at [this project of mine](https://github.com/JoergFiedler/freebsd-ansible-demo).

Requirements
------------

This role is intent to be used with a fresh FreeBSD 10.2 installation. There is a Vagrant Box with providers for VirtualBox and EC2 you may use.

You will find a sample project which uses this role [here](https://github.com/JoergFiedler/freebsd-ansible-demo).

Role Variables
--------------

##### jail_name

The name for the jail. Local part of the hostname. Default: `'{{ jail_net_ip }}'`.

##### jail_domain

The domain this jail belongs to. Domain part of the hostname. Default: `'darkcity'`.

##### jail_net_if

The interface to which the jail's ip address is added. Default: `'lo0'`.

##### jail_net_ip

The jail's ip address. No default value.

##### jail_net_net

The network mask the jail accepts syslog messages from. Default: `'{{ jail_net_ip }}/24'`.

Dependencies
------------

- [JoergFiedler.freebsd-jailed](https://galaxy.ansible.com/detail#/role/6599)

Example Playbook
----------------

    - { role: JoergFiedler.freebsd-jailed-syslogd,
        tags: ['syslogd'],
        ssmtp: true,
        jail_name: 'syslogd',
        jail_net_ip: '10.1.0.2' }

License
-------

BSD

Author Information
------------------

If you like it or do have ideas to improve this project, please open an issue on Github. Thanks.

`dimmaryanto93.jmeter`
=========

Repository ini digunakan untuk menginstall [apache-jmeter](https://www.apache.org/) untuk Linux

Support platform

- Debian
- Ubuntu
- CentOS


Ansible - User Guide
------------

Persiapan yang harus di lalukan, diantaranya

1. Create new user on your server, Recomend using **very-very Strong Password** or using password generator. 
  ```bash
  adduser <username>
  ```

2. Granted to sudoers with NOPASSWD, using `visudo`
  ```ini
  username    ALL=(ALL) NOPASSWD:ALL
  ```

3. Authenticate with private-key for login ssh, generate ssh key on your local machine then use `ssh-copy-id user@your-ip-server` to copy public key to your server.


Requirements
------------

None

Role Variables
--------------

Ada beberapa variable yang temen-temen bisa gunakan untuk setting sonatype nexus-oss, diantaranya seperti berikut:

| Variable name                 | Example value       | Description |
| :---                          | :---                | :---        |
| `jmeter_version`              | `5.4.1`             | Default version download jmeter |
| `jmeter_installation_path`    | `/opt/jmeter`       | Default extract / installation folder |
| `jmeter_user`                 | `jmeter`            | Normal user for running nexus service |

Dependencies
------------

Untuk mengginstall Sonatype Nexus OSS kita membuatuhkan Java Development Kit (JDK) sesuai dengan requirment dari official websiste [seperti berikut](https://help.sonatype.com/repomanager3/installation/system-requirements#SystemRequirements-Linux)

Kita bisa menggunakan role [oracle_java](https://galaxy.ansible.com/dimmaryanto93/oracle_java) atau install manualy


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```ansible
- hosts: servers
  become: true
  roles:
      - { role: dimmaryanto93.jmeter }
```

License
-------

MIT

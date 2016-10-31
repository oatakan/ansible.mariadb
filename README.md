# Mariadb Ansible Role

## Execution Requirements
- Tested on CentOS 7

## Role Variables

The following variables can be overridden:
 * `mariadb_open_firewall`: Default: false. open/close firewalld port 3306
 * `mariadb_secure_installation`: Default: false. Similar to `mysql_secure_installation`
 * `mariadb_root_password`: Default: ''. Pleeeaseeee change :-)
 * `mariadb_db_remove`: Default: [] . List of databases to remove
 * `mariadb_db_create`: Default: [] . List of databases to create
 * `mariadb_user_create`: Default: {}. Dictionary with user credentials, see below.

## Features
Does automatic check of root access and recover root account if no access is granted from content of .my.cnf

# example playbook for this role:
```yaml
- name: Install and configure MariaDB Server
  hosts: vm01
  roles:
   - role: js.mariadb
      mariadb_open_firewall: true
      mariadb_secure_installation: true
      mariadb_root_password: 'nevermind!'
      mariadb_db_create:
       -  db1
       -  db2

      mariadb_db_remove:
       -  database1
       -  database2

      mariadb_user_remove:
        - tom
        - mark

      mariadb_user_create:
        - name: worker1
          password: krypt0
          hosts:
            - "localhost"
          privs:
            - "db1.*:ALL"
            - "db2.*:SELECT,UPDATE"
        - name: app1
          password: krypt0n
          hosts:
            - "web1"
            - "localhost"
          privs:
            - "*.*:ALL"
...
```

# License
Copyright (c) Chris Ruettimann <chris@bitbull.ch>  
This software is licensed to you under the GNU General Public License.  
There is NO WARRANTY for this software, express or  
implied, including the implied warranties of MERCHANTABILITY or FITNESS  
FOR A PARTICULAR PURPOSE. You should have received a copy of GPLv2  
along with this software; if not, see  
http://www.gnu.org/licenses/gpl.txt


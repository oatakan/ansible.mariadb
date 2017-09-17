# Mariadb Ansible Role

## Execution Requirements
- Tested on CentOS 7

## Role Variables

The following variables can be overridden:
 * `mariadb_secure_installation`: Default: false. Similar to `mysql_secure_installation`
 * `mariadb_root_password`: Default: ''.
 * `mariadb_databases`: Default: {} . Dictionary with databases.
 * `mariadb_users_create`: Default: {}. Dictionary with user credentials.
 * `mariadb_users_remove`: Default: {}. Dictionary of users to remove.

## Features
Does automatic check root access and recover root account if no access is granted from content of .my.cnf

## example playbooks for this role are located in `test` folder:
 * `playbook_mariadb_minimal.yml`: Minimal role for testing
 * `playbook_mariadb.yml`: Real life example
 * `playbook_mariadb_full.yml`: Full example with all possible vars.  


# License
https://opensource.org/licenses/LGPL-3.0
Copyright (c) Chris Ruettimann <chris@bitbull.ch>  


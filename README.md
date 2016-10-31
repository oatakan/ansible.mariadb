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

# example playbook for this role
Check the test directory for an example

# License
Copyright (c) Chris Ruettimann <chris@bitbull.ch>  
This software is licensed to you under the GNU General Public License.  
There is NO WARRANTY for this software, express or  
implied, including the implied warranties of MERCHANTABILITY or FITNESS  
FOR A PARTICULAR PURPOSE. You should have received a copy of GPLv2  
along with this software; if not, see  
http://www.gnu.org/licenses/gpl.txt


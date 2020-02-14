Assumptions
------------
1. Server the script is being ran on has internet access for apt-get commands
2. example.com is stored in the user's home directory ( ~/)
3. You've defined your own group vars and inventory file

Libraries Used
--------------

PHP
-----
php[0-9]+.[0-9]+-cli 

php[0-9]+.[0-9]+-fpm 

php[0-9]+.[0-9]+-curl

php[0-9]+.[0-9]+-gd 

php[0-9]+.[0-9]+-mysql 

php[0-9]+.[0-9]+-mbstring


MYSQL
-----
mysql-server 

mysql-client

NINGX
-----
ningx

UNZIP
-----------

unzip

WORDPRESS
---------
WORDPRESS_ZIP=http://wordpress.org/latest.zip

Instructions
-------------
1. Download example.com and wordpress_ansible_installation.yaml files to a target machine
2. Run ansible-playbook -i inventory.yaml wordpress_ansible_installation.yaml

Issues
-------------
If target is an EC2 machines, "Could not get lock /var/lib/dpkg/lock-frontend" errors maybe
generated if playbook is ran immediately after first boot. Typically means ubuntu is still
installing packages, wait for atleast 1 minute.

https://stackoverflow.com/questions/40869900/ansible-script-dpkg-lock-on-aws-launch-ubuntu-16-04

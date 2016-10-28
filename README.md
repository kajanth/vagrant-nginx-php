<b> What? </b>

This vagrantfile (using Virtualbox) creates any number of nginx web-nodes and can provision them using the playbook nginx.yml. 
By default it will create 3 web nodes and they are fronted by a loadbalancer (also running nginx).

inventory
---------
1 x ansible manager - 172.17.177.11
1 x Loadbalancer - http://172.17.177.24/
2 x web servers - 172.17.177.21/172.17.177.22/172.17.177.23

Its a bit ugly but i havent worked with ruby with ruby

There is also a small python script (lbtest.py) that makes a configurable number of requests to the loadbalancer to see if the traffic gets balanced properly.

Ansible Role Name
=================

nginx - Installs and configures an n-node web cluster fronted by a loadbalancer
nginxweb - Installs and configures 2 web nodes
php7 - setup php7 and php7.0-fpm
mysql - install and configure mysql server

Playbook
----------------
To run the playbook, execute 'vagrant up'

1) To Extract file run 'tar -xvf vagrant.tar.gz'
3) cd vagrant
2) Run 'vagrant up'

To do
-----

Automate the node additions by specifying it in the inventory
pull code from git
auto check the configuration
Better script for testing 
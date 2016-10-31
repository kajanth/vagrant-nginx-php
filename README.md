<h2> Vagrant - Ansible - Nginx - LB - Web</h2>

This vagrantfile (using Virtualbox) creates any number of nginx web-nodes and can provision them using the playbook nginx.yml. 
By default it will create 3 web nodes and they are fronted by a loadbalancer (also running nginx).

inventory
---------
1 x ansible manager - 172.17.177.11 </br>
1 x Loadbalancer - http://172.17.177.24/  </br>
3 x web servers - 172.17.177.21/172.17.177.22/172.17.177.23  </br>

Its a bit ugly but i havent worked with ruby


Ansible Role Names
=================

nginx - Installs and configures a web cluster fronted by a loadbalancer
nginxweb - Installs and configures 3 web nodes
php5 - setup php5 and php5.0-fpm
mysql - install and configure mysql server

Playbook
----------------
To run the playbook, execute 'vagrant up'

1) git clone https://github.com/kajanth/vagrant-nginx-php.git </br>
2) cd vagrant-nginx-php</br>
3) Run 'vagrant up'</br>


To do
-----

Automate the node additions by specifying it in the inventory</br>
pull code from git</br>
auto check the configuration</br>
Better script for testing </br>
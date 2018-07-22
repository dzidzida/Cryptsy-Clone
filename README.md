# Cryptsy-Clone

100 % Free Cryptsy Clone

Please consider to make a donation if you using my script

Bitcoin:  1FL1qQiz4HUEakqa9PH5VGH7Ustaqe1stY

Litecoin: LNAXMC2UKpey1ZgD4QXs26jJPTdYj3xryu

Copyright (c) 2014-2015 Adytech Developer Copyright

Pierre Demarque

Installation Instruction
you need php 5.4 and follow instruction http://pastebin.com/CaFXQMQ7

i do installation service + securisation if you need

contact:
adytech2010 at the giant search engine  .com



#License

Cryptsy-Clone is released under the terms of the MIT license. See COPYING for more information or see http://opensource.org/licenses/MIT.

Installation Instruction

sudo apt-get update
sudo apt-get install -y build-essential
sudo apt-get install -y python-software-properties
 
 
sudo add-apt-repository ppa:ondrej/php5
sudo apt-get update
sudo apt-get upgrade
apt-get install apache2
 
sudo apt-get install php5
sudo apt-get install mysql-server libapache2-mod-php5 php5-mysql
sudo apt-get install libboost-all-dev
sudo apt-get install libdb++-dev
sudo apt-get install libminiupnpc-dev
 
-------------
//choisir sa version de libboost
apt-cache show libboost-dev
 
 
//create a vhost
/etc/apache2/sites-available/crypto-maniac.com
mkdir -p /var/www/crypto-maniac.com/public_html
mkdir /var/www/crypto-maniac.com/logs
 
service apache2 restart
 
o7Ym7[]v5n
--------------------
<VirtualHost *:80>
     ServerAdmin webmaster@example.net
     ServerName www.crypto-maniac.com
     ServerAlias www.crypto-maniac.com
     DocumentRoot /var/www/crypto-maniac.com/public_html/
     ErrorLog /var/www/crypto-maniac.com/logs/error.log
     CustomLog /var/www/crypto-maniac.com/logs/access.log combined
 
</VirtualHost>
-------------------------
//enable site
a2ensite crypto-maniac.com.conf
sudo service apache2 reload
//check what module for apache is available to install
apt-cache search libapache2*
 
 
a2enmod rewrite
service apache2 restart
 
a2enmod headers
//add to vhost
Header always append X-Frame-Options SAMEORIGIN
 
-------------------------------------
https://www.digitalocean.com/community/articles/how-to-install-and-secure-phpmyadmin-on-ubuntu-12-04
sudo add-apt-repository ppa:tuxpoldo/phpmyadmin
//install phpmyadmin
sudo apt-get install phpmyadmin  (Anthemis2014OPassword)
sudo nano /etc/apache2/apache2.conf
//add this line
Include /etc/phpmyadmin/apache.conf
//secure phpmyadmin
sudo mysql_secure_installation
 
sudo service apache2 restart
http://www.crypto-maniac.com/phpmyadmin
sudo add-apt-repository --remove ppa:tuxpoldo/phpmyadmin
----------------------------------------------------
add user mysql
create user crypto identified by "passwordhere";
grant all on *.* to crypto with grant option;
 
virer tout les root et mettre un mdp pour www-data (cree le user si pas dispo)
 
----------------------------------------------------------
//fail2ban
https://help.ubuntu.com/community/Fail2ban

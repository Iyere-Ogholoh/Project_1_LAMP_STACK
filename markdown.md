#   LAMP STACK IMPLEMENTATION

##  INSTALLING APACHE2

`sudo apt update`

![updating list of packages](./images/apache_installation/packages_list_update.PNG)

`sudo apt install apache2`

![apache status](./images/apache_installation/apache_status_page1.PNG)

![apache status](./images/apache_installation/apache_status_page2.PNG)

`sudo systemctl status apache2`

![confirming apache2 is running on OS](./images/apache_installation/systemctl_apache2.PNG)

open TCP to port 80 on AWS console

![http port 80 opened](./images/apache_installation/http_port80_secutity_group.PNG)

`curl http://localhost:80`

![curl http](./images/apache_installation/curl_http_page1.PNG)

![curl http](./images/apache_installation/curl_http_page2.PNG)

![curl http](./images/apache_installation/curl_http_page3.PNG)

![curl http](./images/apache_installation/curl_http_page4.PNG)

![curl http](./images/apache_installation/curl_http_page5.PNG)

![curl http](./images/apache_installation/curl_http_page6.PNG)

![curl http](./images/apache_installation/curl_http_page7.PNG)

![curl http](./images/apache_installation/curl_http_page8.PNG)

[testing apache http server](http://35.181.26.164/)

![apache server test](./images/apache_installation/apache_server_test_page1.PNG)

![apache server test](./images/apache_installation/apache_server_test_page2.PNG)

`curl -s http://35.181.26.164/latest/meta-data/public-ipv4`

![public address retrieval](./images/apache_installation/public_ip_address_retrieval.PNG)

### MYSQL installation

`sudo apt update`

![sudo apt update](./images/mysql_installation/sudo_apt_update.PNG)

`sudo apt upgrade`

![kernel upgrade](./images/mysql_installation/kernel_upgrade.PNG)

![outdated libraries](./images/mysql_installation/outdated_libraries.PNG)

![sudo apt upgrade](./images/mysql_installation/sudo_apt_upgrade_page1.PNG)

![sudo apt upgrade](./images/mysql_installation/sudo_apt_upgrade_page2.PNG)

`sudo apt install msql-server`

![sql server installation](./images/mysql_installation/mysql-server_install_page1.PNG)

![sql server installation](./images/mysql_installation/mysql-server_install_page2.PNG)

`sudo service mysql status`

![sql status](./images/mysql_installation/sql_status.PNG)

`sudo mysql`

![sudo mysql](./images/mysql_installation/sudo_mysql.PNG)

set password for root user

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';`

start interactive script

`sudo msql_secure_installation`

![mysql password](./images/mysql_installation/password_setting_page1.PNG)

![mysql password](./images/mysql_installation/password_setting_page2.PNG)

`sudo mysql -p`

![mysql console login](./images/mysql_installation/mysql_login_with_password.PNG)

 INSTALLING PHP

`sudo apt install php libapache2-mod-php php-mysql`

![php installation](./images/php_installation/php_installation.PNG)

`php -v`

![php version check](./images/php_installation/php_version.PNG)

CREATING A VIRTUAL HOST FOR YOUR WEBSITE USING APACHE

`sudo mkdir /var/www/projectlamp`

![creating project lamp directory](./images/creating_virtual_host_using_apache/projectlamp_directory_creation.PNG)

`sudo chown -R $USER:$USER /var/www/projectlamp`

`sudo vi /etc/apache2/sites-available/projectlamp.conf`

`<VirtualHost *:80>
    ServerName projectlamp
    ServerAlias www.projectlamp
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/projectlamp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>`

`sudo ls /etc/apache2/sites-available`

![new files in sites-available directory](./images/creating_virtual_host_using_apache/files_in_sites%20-available_directory.PNG)

`sudo a2ensite projectlamp`

![enabling new virtual host](./images/creating_virtual_host_using_apache/enabling_virtual_host.PNG)

`sudo a2dissite 000-default`

![disabling default website that comes installed with apache](./images/creating_virtual_host_using_apache/default_apache_website_disabling.PNG)

![disabled apache default website](./images/creating_virtual_host_using_apache/apache_default_website_dissabled.PNG)

`sudo apache2ctl configtest`

![checking for configuration syntax errors](./images/creating_virtual_host_using_apache/config_syntax_check.PNG)

`sudo systemctl reload apache2`

`sudo echo 'Hello LAMP from hostname' $(curl -s http://15.188.53.3/latest/meta-data/public-hostname) 'with public IP' $(curl-s http://15.188.53.3/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html`

[public ip address](http://15.188.53.3/)

![website url showing  echo command](./images/creating_virtual_host_using_apache/website_url.PNG)

[public dns](http://ec2-15-188-53-3.eu-west-3.compute.amazonaws.com/)

![public dns access to website](./images/creating_virtual_host_using_apache/public_dns.PNG)

ENEABLING PHP ON WEBSITE

sudo vim /etc/apache2/mods-enabled/dir.conf

`<IfModule mod_dir.c>
        #Change this:
        #DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm
        #To this:
        DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>`

![vim changing order of index.html and index.php](./images/php_installation/changing_order_of_index.html%26index.php.PNG) 

`sudo systemctl reload apache2`

vim /var/www/projectlamp/index.php
        
`<?php
phpinfo();`

![php test script](./images/php_installation/php_test_script.PNG)

![php script web page](./images/php_installation/php_script_web_page.PNG)

`sudo rm /var/www/projectlamp/index.php`

![php script web page removed](./images/php_installation/php_script_web_page_removed.PNG)





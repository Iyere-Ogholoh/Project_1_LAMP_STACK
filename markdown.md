#   LAMP stack implementation

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

## MYSQL installation

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

### 






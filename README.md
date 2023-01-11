
# Unbound DNS Server Web Interface

We searched a lot of web interfaces for Unbound DNS Server but couldn't find any worthwhile one.

We tried to enable the community to manage Unbound DNS in a more useful way, especially in test environments.

If you have any requests, please let us know.


## Requirements and Installation Steps

#### Unbound Installation
```
#sudo apt-get update
#sudo apt-get install unbound
#sudo touch /etc/unbound/host_entries.conf
#sudo chmod 777 /etc/unbound/host_entries.conf
```

#### Apache, PHP, Mysql Installation
```
#sudo apt-get install git
#sudo apt install software-properties-common
#sudo add-apt-repository ppa:ondrej/php
#sudo apt-get install apache2
#sudo apt-get install php8.2 php8.2-common php8.2-mysql php8.2-cli
#sudo apt-get install mariadb-server
#sudo mysql_secure_installation
```

#### Database Configuration
```
#sudo mysql -u root -p
#Mysql> create database unbound;
#Mysql> create user 'dns_user'@'localhost' identified by 'Unb0undP@ss23';
#Mysql> grant all privileges on unbound.* to 'dns_user'@'localhost';
#Mysql> flush privileges;
#Mysql> use unbound;
#Mysql> create table users(
   id INT NOT NULL AUTO_INCREMENT,
   username VARCHAR(100) NOT NULL,
   password VARCHAR(255) NOT NULL);
#Mysql> insert into users (id, username, password) values (1,'dnsadmin', '$2y$10$Ud3yKKJZ8iYPXoDsiSBGE.ONBztPWF6EEUEbnNSaaPheEjWqAytRy');
```

Set your mysql root password and type Y for all questions.

#### Application Installation
```
#cd /tmp
#git clone https://github.com/kdrypr/Unbound-Web-Interface.git
#sudo mkdir /var/www/unbound
#cd Unbound-Web-Interface
#sudo mv * /var/www/unbound/
#sudo rm /var/www/unbound/README.md
#sudo chown www-data:www-data /var/www/unbound/
#sudo mv /var/www/unbound/unbound.conf /etc/unbound/unbound.conf
#sudo chown root:root /etc/unbound/unbound.conf
```

#### Features
* Add New DNS Record ( A and MX )
* Edit DNS Record
* Remove DNS Record
* Reload Unbound DNS Server

#### Support Team
* [Faik COŞKUN](https://github.com/faikcoskun)
* [Merve Latife YAPAR](https://github.com/mrvsay)

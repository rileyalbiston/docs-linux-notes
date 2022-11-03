# Setup LAMP stack with Wordpress

[How To Install Linux, Apache, MySQL, PHP (LAMP) stack on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu-20-04)

[How to Install Apache, MySQL & PHP on Ubuntu 20.04](https://tecadmin.net/install-lamp-ubuntu-20-04/)

**Wordpress**

[How To Install WordPress on Ubuntu 20.04 with a LAMP Stack](https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-on-ubuntu-20-04-with-a-lamp-stack)

[How to install WordPress on Ubuntu Linux](https://hands-on.cloud/how-to-install-wordpress-on-ubuntu-linux/)

## Before You Get Started

* I'll using Ubuntu desktop. Will also work with Ubuntu server. Would likely work on most Ubuntu derivitive distro.

## Install Apache

Now upgrade current packages to latest version.

```
sudo apt update && sudo apt upgrade 
```

or

```
sudo apt update 

sudo apt upgrade
```

Then to install the Apache2 package:

```
sudo apt install apache2 
```

In a browser visit:

[127.0.0.1](127.0.0.1)

To check the Apache2 service status:

```
sudo systemctl status apache2 
```

## Install PHP

If you’re using Apache as your web server, run the following commands to install PHP and Apache PHP module:

```
sudo apt update
sudo apt install php libapache2-mod-php
```

Once the packages are installed, restart Apache for the PHP module to get loaded:

```
sudo systemctl restart apache2
```

## Install MySQL

The default Ubuntu 20.04 apt repositories contains MySQL server 8.0. Finally, install mysql-server packages for the MySQL database. Also, install the php-mysql package to use MySQL support using PHP. Use the following command to install it.

```
sudo apt install mysql-server php-mysql 
```

Once the installation is complete, the MySQL server should be started automatically. You can quickly check its current status via systemd:

```
sudo service mysql status
```

Log into MySQL

```
sudo mysql
```

List databases

```
SHOW DATABASES;
```

Exit mysql

```
\q
```

When the installation is finished, it’s recommended that you run a security script that comes pre-installed with MySQL. This script will remove some insecure default settings and lock down access to your database system. Start the interactive script by running:

```
sudo mysql_secure_installation
```

This will ask if you want to configure the VALIDATE PASSWORD PLUGIN.

```
Securing the MySQL server deployment.

Connecting to MySQL using a blank password.

VALIDATE PASSWORD COMPONENT can be used to test passwords
and improve security. It checks the strength of password
and allows the users to set only those passwords which are
secure enough. Would you like to setup VALIDATE PASSWORD component? 

Press y|Y for Yes, any other key for No: y

There are three levels of password validation policy:

LOW    Length >= 8
MEDIUM Length >= 8, numeric, mixed case, and special characters
STRONG Length >= 8, numeric, mixed case, special characters and dictionary  file

Please enter 0 = LOW, 1 = MEDIUM and 2 = STRONG: 2
Please set the password for root here.

New password:

Re-enter new password:

Estimated strength of the password: 100
Do you wish to continue with the password provided?(Press y|Y for Yes, any other key for No) : y
By default, a MySQL installation has an anonymous user,
allowing anyone to log into MySQL without having to have
a user account created for them. This is intended only for
testing, and to make the installation go a bit smoother.
You should remove them before moving into a production
environment.

Remove anonymous users? (Press y|Y for Yes, any other key for No) : y
Success.


Normally, root should only be allowed to connect from
'localhost'. This ensures that someone cannot guess at
the root password from the network.

Disallow root login remotely? (Press y|Y for Yes, any other key for No) : y
Success.

By default, MySQL comes with a database named 'test' that
anyone can access. This is also intended only for testing,
and should be removed before moving into a production
environment.


Remove test database and access to it? (Press y|Y for Yes, any other key for No) : y
 - Dropping test database...
Success.

 - Removing privileges on test database...
Success.

Reloading the privilege tables will ensure that all changes
made so far will take effect immediately.

Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y
Success.

All done!
```


## Installing phpMyAdmin (optional) - Hasen't worked so far

phpMyAdmin provides a user friendly web interface to manage MySQL database server. You can install phpMyAdmin on Ubuntu 20.04 by executing the following command:


```
sudo apt install phpmyadmin 
```

The installation process will prompt to select web server to configure. Select “Apache” as web server to run phpMyAdmin.


Very Important!!!!!!!!!!!!!!!!!!!!
```
When the first prompt appears, apache2 is highlighted, but not selected. If you do not hit "SPACE" to select Apache, the installer will not move the necessary files during installation. Hit "SPACE", "TAB", and then "ENTER" to select Apache.
```

Next, this will prompt to create database for phpMyAdmin and prompt for the administrative user access details. Complete all steps to finish phpMyAdmin installation.



## Manage Services

**Start, Stop and Restart Apache on Ubuntu**

To start the Apache service, execute the following command:

```
sudo systemctl start apache2
```

To stop the Apache service, execute the following command:

```
sudo systemctl stop apache2
```

Whenever you make changes to the Apache configuration, you need to restart the server processes. To restart the Apache service, run:

```
sudo systemctl restart apache2
```


## Adjusting Firewall Rules


## Test Setup

After completing all setup. Let’s create a info.php file website document root with following content.

```
sudo echo "<?php phpinfo(); ?>" > /var/www/html/info.php 
```

Now access this file in web browser. You will see the screen like below with all details of PHP on server.


[127.0.0.1/info.php](127.0.0.1/info.php)


## Install Wordpress

[Install and configure WordPress](https://ubuntu.com/tutorials/install-and-configure-wordpress#1-overview)



a

a

# Nextcloud install on Linux Mint

**Date:** 05 Oct 2022
**OS:** Linux Mint 20.2



https://docs.nextcloud.com/server/latest/admin_manual/installation/example_ubuntu.html
https://linuxiac.com/install-nextcloud-on-ubuntu/

1. Get the system ready
```bash
sudo apt update && sudo apt upgrade
```

2. Install dependencies 
```bash
sudo apt install apache2 mariadb-server libapache2-mod-php php-gd php-mysql \
php-curl php-mbstring php-intl php-gmp php-bcmath php-xml php-imagick php-zip
```

Check verion of required software
```bash
mysql -V
apache2 -version
php -version
```

3. Setup database
3.1. To start the MySQL command line mode
```bash
sudo mysql
or
sudo mysql -u root -p
```

3.2. Setup database and user
```bash
CREATE USER 'nextcloud-user'@'localhost' IDENTIFIED BY '336514';
CREATE DATABASE IF NOT EXISTS nextcloud CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;
GRANT ALL PRIVILEGES ON nextcloud.* TO 'nextcloud-user'@'localhost';
FLUSH PRIVILEGES;
```

Confirm can connect with the new user
```bash
mysql -u nextcloud-user -p
```


3.3. Exit MySQL command line
```bash
quit;
```


4. Download and install Nextcloud
https://nextcloud.com/install/#instructions-server

```bash
wget https://download.nextcloud.com/server/releases/nextcloud-25.0.0.zip
```

5. Unzip and  create data directory
```bash
sudo unzip nextcloud-25.0.0.zip -d /var/www/html/
sudo mkdir /var/www/html/nextcloud/data
sudo chown -R www-data:www-data /var/www/html/nextcloud/
```

6. Configure Nextcloud


`http://server-ip/nextcloud/`


[http://127.0.0.1/nextcloud/](http://127.0.0.1/nextcloud/)

7. Setup Admin user
un: admin
pw: admin

----------------------------
## Testing stuff here

```bash
Alias /nextcloud "/var/www/html/nextcloud/"

<Directory /var/www/html/nextcloud/>
  Require all granted
  AllowOverride All
  Options FollowSymLinks MultiViews

  <IfModule mod_dav.c>
    Dav off
  </IfModule>
</Directory>
```


a2ensite nextcloud.conf

systemctl reload apache2


Had to stop nginx because it was on port 80. Should look at running them on different ports.
√NGINX

- apt install nginx
- cd /etc/nginx/sites-available
- nano default
- beri pagar pd listen ipv6
- apt install links zip wget
- systemctl restart nginx


- apt install ca-certificates apt-transport-https curl lsb-release
- curl -fsSL https://packages.sury.org/php/README.txt |
> bash
- apt install php8.0 php8.0-fpm php8.0-mysql php8.0-intl php8.0-gd php8.0-mbstring php8.0-curl php8.0-zip php8.0-simpleXML
- cd /var/www/html
-nano infophp.php
<? php
phpinfo() ;
? >
- cd /etc/nginx/sites-available
- nano default 
tambah index. php di #add index. php
hapus # 4 baris dan ganti versi
- systemctl restart nginx dan php8.0-fpm
- uji di browser http://ip/infophp.php
- cd /etc/php
- cd 8.0
- edit file php. ini  "display error = On" di direk cli dan fpm
- systemctl restart php8.0-fpm


- apt install mariadb-server mariadb-client
-mariadb
-membuat password user 
alter user 'root'@'localhost' identified by 'password';
flush privileges;
- mariadb -u root -p 
- create database ....... db;
- create user'.... '@'localhost'identified by'pswd';
- grant all privileges on...... db. *to'use'@'localhost'identified by'pswd;
- flush privileges;
- exit;


-cd /var/www/html
-ls
-nano konek-db. php
-<?php
$servername = "localhost";
$username = "anangnurman";
$pswd  = "admin123";
$database = "dbanang";

$koneksi = mysqli_connect($servername, $username, $pswd, $database);

if (!$koneksi){
                die("Koneksi database gagal".mysqli_connect_error());
}
echo "Koneksi database sukses"; 
mysqli_close($koneksi);
? >
-uji http://ip/konek-db.php


-cd /var/www/html
-ls
-rm index. nginx-debian. html
-wget https://ukk25.smekindo.biz.id/prestashop_8.2.0.zip
-ls
-unzip prestashop_8.2.0.zip (mengekstrak) 
-ls
-rm index. php
-unzip prestashop. zip
-chown -R www-data:www-data *
-chmod 755/777 -R *
-uji di google http://ip/install
-pada back office disuruh hps folder install dan rename admin
-rm -rf install/
-mv admin / .... /

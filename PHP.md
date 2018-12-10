### Install PHP 7
```
sudo apt-get update
sudo apt-get install -y ghostscript
sudo apt-get install -y imagemagick
sudo apt-get install -y php
sudo apt-get install -y apache2
sudo apt-get install -y libapache2-mod-php
sudo apt-get install -y php-mysql
sudo apt-get install -y php-gd
sudo apt-get install -y php-curl
sudo apt-get install -y php-imagick
sudo apt-get install -y php-mcrypt
sudo apt-get install -y php-mbstring
```
```
sudo apt-get install php7.0-dev
https://github.com/phpv8/v8js/blob/master/README.Linux.md
```
### Add ubuntu to www dir
```
sudo adduser ubuntu www-data
sudo chown -R www-data:www-data /var/www
sudo chmod -R g+rwX /var/www
```
### Upload php chmod
```
chmod 755 -R uploads/
```
### Enable rewrite apache
```
sudo a2enmod rewrite
sudo /etc/init.d/apache2 restart
```
### /etc/apache2/apache2.conf:
```
<Directory />
    Options FollowSymLinks
    AllowOverride All
    Require all granted
</Directory>

<Directory /usr/share>
    AllowOverride All
    Require all granted
</Directory>

<Directory /var/www/>
    Options Indexes FollowSymLinks
    AllowOverride All
    Require all granted
</Directory>
```
### Add site
```
a2ensite ajudai.test.4all.com.conf
```
### Remove site
```
a2dissite 000-default.conf
```
### Site conf location
```
/etc/apache2/sites-available/example.com.conf
```
### Conf exemple
```
<VirtualHost *:80>
    ServerAdmin admin@example.com
    ServerName example.com
    ServerAlias www.example.com
    DocumentRoot /var/www/example.com/public_html
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
    <Directory "/var/www/example.com/public_html">
        AllowOverride All
    </Directory>
</VirtualHost>
```

### .htaccess

```
<IfModule mod_setenvif.c>
  SetEnvIf X-Forwarded-Proto "^https$" HTTPS
</IfModule>
```

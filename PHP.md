sudo apt-get update
sudo apt-get install -y python-software-properties
sudo add-apt-repository ppa:ondrej/php5
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
 
 
sudo adduser ubuntu www-data
sudo chown -R www-data:www-data /var/www
sudo chmod -R g+rwX /var/www
 
chmod 755 -R uploads/
 
sudo a2enmod rewrite
sudo /etc/init.d/apache2 restart
 
https://www.digitalocean.com/community/tutorials/como-configurar-apache-virtual-hosts-no-ubuntu-14-04-lts-pt
 
// Add site
a2ensite ajudai.test.4all.com.conf
// Remove site
a2dissite 000-default.conf
 
/etc/apache2/sites-available/example.com.conf
 
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

--> whats sudo ?
The sudo command allows you to run programs with the security privileges of another user (by default, as the superuser)

--> apt-get 
It allows you to search for, install, manage, update, and remove software.
The most common commands under apt-get are:

sudo apt-get install (to install a package)
sudo apt-get remove (package removal)
sudo apt-get update (for updating a package)
sudo apt-get upgrade (for upgrading a package)
apt-get help (to know more about a command )
Here, sudo is used for providing you with the security privileges of a superuser.

--> ip address:
172.31.36.14

--> checkpoint 6:
chgrp changes the ownership of a folder
chmod changes the permission of a file

--> how to deploy: 
. Connecting to the server and downloading its packages:
ssh -i yourKey.pem ubuntu@address
apt-get install the packages
a2enmod rewrite
restart apache2 : sudo /etc/init.d/apache2 restart

. Uploading the website onto the server:
git clone the repository in var/www/html, and if it doesn't exist, create it
Install composer:
run curl -sS https://getcomposer.org/installer | sudo php -- --install- dir=/usr/local/bin --filename=composer 
run composer i in the repository 

. Creating your app environment and generating a key:
copy the .env.example and change its name to .env : cp .env.example .env
vim .env and change the app name to your preferences but without whitespaces
run php artisan key:generate

. Configuring apache2: 
find its path: apache2 -V
vim apache2.conf and add ur website directory
cd sites-enabled
vim 000-default.conf and add your admin and the website root
restart apache2 : sudo /etc/init.d/apache2 restart

. Setting up the folders:
go to the repository
run sudo chgrp -R www-data storage bootstrap/cache
run sudo chmod -R ug+rwx storage bootstrap/cache
your website should be done and ready for people to visit it

# install apache2 & mysql & maridb & phpmyadmin on debian 5.15.5
# Simple and without extras

# install apache2 :
sudo apt-get install apache2

# dependency error :
   sudo apt-get install apache2-utils
   
# install mysql server :
sudo apt-get install mysql-server

# has no installation candidate : 
   sudo apt-get install maridb-server
   
# install phpmyadmin & tools :
sudo apt-get install php libapache2-mod-php php-mysql php-curl php-gd php-json php-mcrypt php-zip
sudo apt-get install phpmyadmin
! q : select apache2 

sudo service apache2 restart

# change phpmyadmin password:
sudo mysqladmin -u root password 'YOURpASS'   

# phpmyadmin NotFound Error:
sudo -H gedit /etc/apache2/apache2.conf
//nano-vim-vi-edit-gedit

# add this:
Include /etc/phpmyadmin/apache.conf

# permission error :
cd /var/www/
sudo chmod 777 o-rwx html/

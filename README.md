# Installing Apache2, MySQL, MariaDB, and phpMyAdmin on Debian 5.15.5

## Step 1: Install Apache2
To install the Apache2 web server, run the following command:

```bash
sudo apt-get install apache2
```

If you encounter a dependency error, install the required utilities:

```bash
sudo apt-get install apache2-utils
```

## Step 2: Install MySQL Server
To install MySQL Server, execute:

```bash
sudo apt-get install mysql-server
```

## Step 3: Install MariaDB Server (if MySQL is not available)
If MySQL is not available in your repository, install MariaDB instead:

```bash
sudo apt-get install mariadb-server
```

## Step 4: Install phpMyAdmin and PHP Modules
Install phpMyAdmin along with the required PHP modules:

```bash
sudo apt-get install php libapache2-mod-php php-mysql php-curl php-gd php-json php-mcrypt php-zip
sudo apt-get install phpmyadmin
```

During installation, select `apache2` when prompted.

## Step 5: Restart Apache2
Restart the Apache2 service to apply changes:

```bash
sudo service apache2 restart
```

## Step 6: Change phpMyAdmin Password
To set or change the phpMyAdmin root password, run:

```bash
sudo mysqladmin -u root password 'YOUR_PASSWORD'
```

## Step 7: Fix phpMyAdmin Not Found Error
If phpMyAdmin is not accessible, edit the Apache configuration file:

```bash
sudo nano /etc/apache2/apache2.conf
```

Add the following line at the end of the file:

```apache
Include /etc/phpmyadmin/apache.conf
```

Save the file and restart Apache:

```bash
sudo service apache2 restart
```

## Step 8: Fix Permission Issues
If you encounter permission errors, adjust the permissions of the web directory:

```bash
cd /var/www/
sudo chmod 777 -R html/
```

## Conclusion
You have successfully installed Apache2, MySQL (or MariaDB), and phpMyAdmin on Debian 5.15.5. Your server should now be ready for development or deployment.


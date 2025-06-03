# Install PHP
PHP, which stands for PHP: Hypertext Preprocessor, is the fourth and final layer of the LAMP stack. It is a scripting language that allows websites to run dynamic processes. A dynamic process involves information in software that constantly changes. Web developers embed the PHP programming language in HTML to show real-time or updated information on websites. They use PHP to allow the web server, database, and operating system to cohesively process requests from browsers.

Step 6: Install PHP on Ubuntu

1. Install PHP along with some common PHP extensions. These extensions will allow PHP to work with MySQL and other functionalities you might need. `sudo apt install php php-mysql php-fpm libapache2-mod-php php-cli php-json php-common php-mbstring php-zip php-gd php-xml php-curl`

2. Check the installed PHP version to ensure it’s installed correctly. php -v

3. You need to tell Apache to use PHP by modifying the default configuration file. WHY; Apache is designed to serve HTML files by default. To enable it to process PHP files, you need to configure it to recognize and handle PHP code. For instance, without this configuration, if you navigate to a PHP file on your server, Apache would try to serve the file as plain text rather than executing the PHP code within it. By updating the DirectoryIndex directive in the configuration file, you specify which file Apache should serve by default when a directory is accessed. Adding index.php to the DirectoryIndex directive tells Apache to prioritize index.php over other files like index.html. This is important because it ensures that your PHP application’s homepage (often an index.php file) is served correctly.

Let's go;

- Open the Apache configuration file: `sudo nano /etc/apache2/mods-enabled/dir.conf`

- Adjust the DirectoryIndex directive to prioritize index.php:

```
<IfModule mod_dir.c>
    DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>
```

- Save and close the file (Ctrl + X, Y, Enter).

4. Restart Apache to apply the changes. sudo systemctl restart apache2

5. Create a PHP info file to test the PHP installation.

- Create the file: `sudo nano /var/www/html/info.php`

6. Add the following content;

```
<?php
phpinfo();
?>
```

- Save and close the file.
- Open your web browser and go to http://your-server-ip/info.php. You should see a page displaying PHP information, which means PHP is installed and working correctly.

7. Deploy a Simple PHP Application
- Create a new PHP file in the Apache root directory: `sudo nano /var/www/html/index.php`
- Add the following content to the file:

```
<?php
echo "Hello, World!, I am learning DevOps";
?>
```

Navigate to http://localhost or your server's IP address in your web browser. You should see "Hello, World!, I am learning DevOps" displayed on the page.

Congratulations, You have finished your very first REAL WORLD PROJECT by deploying a LAMP stack website in AWS Cloud!

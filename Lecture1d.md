# Install MySQL
MySQL is an open-source relational DataBase Management System (DBMS)](https://en.wikipedia.org/wiki/Database#Database_management_system) and is the third layer of the LAMP stack. The LAMP model uses MySQL for storing, managing, and querying information in relational databases. For example, developers store application data, such as customer records, sales, and inventories etc. When a user searches for information, the web server queries the stored data in MySQL. Query refers to special instructions for manipulating data in a relational database with the SQL language.

Step 5: Install MySQL

1. Install MySQL server: sudo apt install mysql-server -y

2. Start the MySQL service and enable it to start on boot:

``` bash
sudo systemctl start mysqld
sudo systemctl enable mysqld
```

3. Run the security script to set up a root password and other security settings: sudo mysql_secure_installation For the rest of the questions, press Y and hit the ENTER key at each prompt.
4. Verify Installation: Log in to MySQL: `sudo mysql -u root -p`
5. Exit the MySQL shell with: `exit`




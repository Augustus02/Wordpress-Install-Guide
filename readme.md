
# How to install WordPress on your ubuntu 16.04 server.

### For wordpress to work on your server you will need to install PHP and MySQL.

## Step 1. 

ssh onto your server from your local terminal.

make sure your server is up to date by running: sudo apt-get update 

## Step 2. Install PHP 7.2

#### To install PHP 7.2 you will need to run the following commands.

* sudo add-apt-repository ppa:ondrej/php
* sudo apt-get update
* sudo apt-get install php7.2

## Step 3. Install MySQL

#### To install MySQL, you need to do the following steps.

Run this command: sudo apt-get install mysql-server 

Make a password that you will remember (We will need it later on)

(Optional) If you want to make mysql more secure then run the following command and answer the questions: mysql_secure_installation 

Then check the status of mysql with: sudo service mysql status 

## Step 4. Add the following extensions

Run the following commands  

* sudo apt-get install libApache2-mod-php7.2 
* sudo apt-get install php7.2-mysql 
* sudo apt-get install php7.2-mbstring 
* sudo service apache2 restart 

## Step 5. Installing WordPress 

Navigate into your web root directory  

Then run: sudo curl -O https://wordpress.org/latest.zip

This command installs a program to allow you to unzip files: sudo apt-get install unzip 

Now you can unzip latest.zip using: sudo unzip latest.zip 

Move into the wordpress directory using: cd wordpress/ 

## Step 6. Create a Database

**Anything inbetween <> will be your own information. you will need to replace the text and the <> for the commands to work. Do not replace anything else**

we will now login to mysql using: sudo mysql -u root -p

Enter your password for mysql

Now run the following commands

* CREATE DATABASE < database name >;

* CREATE USER '< username >'@'localhost' IDENTIFIED BY '< password >';

* GRANT ALL PRIVILEGES ON < database made above >.* TO '< your username made above >'@'localhost';

You should be able to see your database using: SHOW DATABASES;

now run: FLUSH PRIVILEGES;

now you can exit out of mysql using: exit 

You need to remeber your database name, your username, and your password

## Step 7. Restart mysql and apache2

run the following commands

* sudo service mysql restart
* sudo service apache2 restart
* sudo apt-get update

## Step 8. Final steps

Now you can visit your site in the browser 

add /wordpress at the end of the url

Login using the credentials we made in Step 6 but leave (Database host) as localhost.

Now go back to your terminal and enter the following commands

Create a wp-config file using: sudo touch wp-config.php 

Edit the file using: sudo nano wp-config.php  

Now paste the code they provided on the site into wp-config.php 

Save the file using: control o

Then exit out using: control x

You can now go back to your site in the browser 

enter your credentials

Then press install  

Now you are done! 
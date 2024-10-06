# WEB-STACK-IMPLEMENTATION-LAMP-STACK-IN-AWS

# Purpose of this Project: 
This project helps to further develop deep understanding on the following

  •Linux Terminal  
  •Understanding on web technology stack such as LEMP  
  •Components of LEMP Stack: LINUX, NGINX, MYSQL, PHP  
  •How the LEMP stack works
# What is LEMP Stack?
The LEMP stack is a collection of software used to serve dynamic websites and web applications. It is an acronym that stands for:
  1. Linux: The operating system (usually a Linux-based distribution like Ubuntu or CentOS) that forms the foundation of the stack.
  2. Engine-X (Nginx): The web server software that serves the web content. It acts as a reverse proxy server, handling HTTP requests.
  3. MySQL (or MariaDB): The relational database management system that stores website data.
  4. PHP (or Python/Perl): The programming language that processes dynamic content and communicates with the database.
# Stages Involved:

•	Stage 0: Preparing Prerequisite. Creating an AWS account and a virtual server with Ubuntu Server OS.

•	Stage 1: Install Nginx and Updating the Firewall.

•	Stage 2: Install MySQL.

•	Stage 3: Install PHP.

•	Stage 4: Create a Virtual Host for your Website using Apache.

# Stage 0: Preparing Prerequisite. 

## 1.	Create an AWS account and a virtual server with Ubuntu Server OS. 
  This same process used during the LAMP project was used here.
# Stage 1: Updating the firewall and Install Nginx

## What is Nginx: 
The web server software that serves the web content. It acts as a reverse proxy server, handling HTTP requests. Nginx handles incoming requests from users' browsers.
## 1. Using the apt package manager, Upadte all packages in package manager and install Nginx
      sudo apt update

      sudo apt install nginx
![5](https://github.com/user-attachments/assets/2d0ab27b-ed56-4fc6-9e31-fe0af868a3ea)

## 3. Verify that nginx is running as a service on the OS.

      sudo systemctl status nginx

      Note: If it is green and running, then nginx is running perfectly
      
![7](https://github.com/user-attachments/assets/09948c4d-5462-41d5-9cbd-b3b75f2679c5)

## The server can be accessed locally by using the commands below

      curl http://localhost:80   
                or               
      curl http://127.0.0.1:80
![9](https://github.com/user-attachments/assets/98af6f3d-50e4-4371-90e1-558ea66c42a8)

## Test how our Nginx server can respond to requests from the Internet. 

   Open a web browser of your choice and try to access following url
   
   http://<"Public ip address">:80-- "In place of the 'Public-IP-Address' Use the public ip address on the instance page"
   
   Note: If the page is displayed, then the web server is now correctly installed and accessible through your firewall.
   
![10](https://github.com/user-attachments/assets/1568cae4-8bcc-4918-9d01-3f9354ac1127)

# Stage 2: Installing MYSQL

##    What is MYSQL

MySQL is an open-source relational database management system used to store, manage, and retrieve data for web applications. It is used to Store information like user accounts, product details, and content in an organized, easily queryable format.

## 1. Install the mysql-server

      $ sudo apt install mysql-server

When prompted, confirm installation by typing Y, and then ENTER.

![image](https://github.com/user-attachments/assets/c2d07a5a-9e88-4b42-bb56-d2d902507572)

## 2. Log in to the MySQL console by typing:

      $ sudo mysql
      
## 2. Log in to the MySQL console by typing:

      $ sudo mysql

![image](https://github.com/user-attachments/assets/5270204a-aad8-41e1-96d5-eb6fac0e1f4a)

## 3. Set a password for the root user.

      ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';

 ## Result

![image](https://github.com/user-attachments/assets/31967ca9-8558-45bd-9b89-4782130acea3)

## Exit mysql

      exit

## Run the Interactive script command

      sudo mysql_secure_installation
      
The command "$ sudo mysql_secure_installation" is used to improve the security of your MySQL installation by performing a few essential security-related tasks.

a. Protect your MySQL server from unauthorized access.

b. Prevent remote root access (if not needed).

c. Ensure your installation is more resilient to attacks.

![image](https://github.com/user-attachments/assets/0b22530d-cdf0-4252-8f6b-fe0f33e772e2)

Press y to set-up VALIDATE PASSWORD component

![image](https://github.com/user-attachments/assets/d72ad011-403a-41bb-9769-0a8e3c39173b)

Enter 0,1 or 2 to choose which level of password validation policy you wish

![image](https://github.com/user-attachments/assets/4db9b999-8bce-46fd-aa20-1e50318ae7fc)

Enter y to continue

![image](https://github.com/user-attachments/assets/81406f49-12b3-4015-b912-12b50791a98a)

Enter the desired password

![image](https://github.com/user-attachments/assets/1b9dbf19-e788-4a5a-847c-b85e98d8cb51)

Press y to continue.

For the rest of the question press y and hit enter at each prompt.

![image](https://github.com/user-attachments/assets/4f348ce1-cd6b-4351-98d3-e6cc6dee1386)

## Log in to the MYSQL CONSOLE after changing the user root pasword by using

      sudo mysql -p

Enter the new password when promped to

![image](https://github.com/user-attachments/assets/e4ccdb80-e9f6-48b0-8446-70e2cbcc4cef)

Exit the MYSQL console

      exit

![25](https://github.com/user-attachments/assets/8b1cdbff-450f-4fe9-94e9-2255c8cf1ec7)

# Stage 3. Installing php-fpm and php-mysql

  While Apache embeds the PHP interpreter in each request, Nginx requires an external program to handle PHP processing and act as a bridge between the PHP interpreter itself and the web server. This allows for a better overall performance in most PHP-based websites, but it requires additional configuration. You'll need to install php-fpm, which stands for "PHP fastCGI process manager", and tell Nginx to pass PHP requests to this software for processing. Additionally, you'll need php-mysql, a PHP module that allows PHP to communicate with MySQL-based databases. Core PHP packages will automatically be installed as dependencies.
  
  The two packages can be installed at once:
  
        sudo apt install php-fpm php-mysql

  ![26](https://github.com/user-attachments/assets/e13257c8-0df4-460f-b231-e527e97bb846)

  # Stage 4. Configuring Nginx to use PHP Processor

  To host multiple sites,  we'll create a directory structure within /var/www with the domain name projectLEMP.

  ## 1. Create the root web directory for your_domain as follows:

      sudo mkdir /var/www/projectLEMP

  ## 2. Assign ownership of the directory to my current system user using the $USER environment variable
   
      sudo chown -R $USER:$USER /var/www/projectLEMP
      
  ## 3. Open a new configuration file in Nginx'S sites-available directory using nano

    sudo nano /etc/nginx/sites-available/projectLEMP

This will create a new blank file. Paste in the following bare-bones configuration:

![image](https://github.com/user-attachments/assets/37291bfb-0945-45c2-b018-6422d02fd76e)

  ## 4. Activate the configuration by linking to the config file from Nginx's sites-enabled directory:

    sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/

  ## 5. Test the configuration for syntax error 

      sudo nginx -t

  ![27](https://github.com/user-attachments/assets/6d531c03-c6a0-4557-a325-018215e02ce2)

  ## 6. Disable default Nginx host that is currently configured to listen on port 80

    sudo unlink /etc/nginx/sites-enabled/default

  ## 7. Reload Nginx to apply the changes

    sudo systemctl reload nginx

  ## 8. Create an index.html file in the web root 

    To test the server block is working well, create an index.html in the web root /var/www/projectLEMP/

sudo bash -c 'echo "Hello LAMP from hostname $(TOKEN=$(curl -X PUT \"http://169.254.169.254/latest/api/token\" -H \"X-aws-ec2-metadata-token-ttl-seconds: 21600\") && curl -H \"X-aws-ec2-metadata-token: $TOKEN\" -s http://169.254.169.254/latest/meta-data/public-hostname) with public IP $(TOKEN=$(curl -X PUT \"http://169.254.169.254/latest/api/token\" -H \"X-aws-ec2-metadata-token-ttl-seconds: 21600\") && curl -H \"X-aws-ec2-metadata-token: $TOKEN\" -s http://169.254.169.254/latest/meta-data/public-ipv4)" > /var/www/projectlamp/index.html'

  ## 9. Open a website using the public ip address
   ## Output

![29](https://github.com/user-attachments/assets/72af546c-c62e-4616-aeb1-1e09c7cc3181)

  ## 10. The website can also be accessed using public DNS name

    http://<Public-DNS-Name>:80

# Stage 5. Testing PHP with Nginx

  ## 1. Create a test PHP file in the document web root

  At this point, the LEMP stack is completely installed and fully operational.

  You can test it to validate that Nginx can correctly handle .php files off to your PHP processor. This can be done by creating a test PHP file in your document root. Open a new file
called info.php within the document root in the text editor:

    sudo nano /var/www/projectLEMP/info.php

Paste the valid PHP Code

![image](https://github.com/user-attachments/assets/b2e87bf6-c256-402f-b27c-3410681c8410)


![30](https://github.com/user-attachments/assets/1ebe5250-d84a-4f3b-aec0-6f336dc7b3fd)

  ## 2. Access the page in the web browser
  You can now access this page in the web browser by visiting the domain name or public IP address set up in your Nginx configuration file, followed by /info.php:

      http://'server_domain_or_IP'/info.php

  ## Output

  ![31](https://github.com/user-attachments/assets/3fb982ea-eae5-419a-8a2e-b72cea00adac)

  ##### Note: it's best to remove the file you created as it contains sensitive information about your PHP environment and your Ubuntu server. You can use 'rm' to remove that file. You can always regenerate this file if you need it later.


      $ sudo rm /var/www/your_domain/info.php

# Stage 6: Retrieving data from MySQL database with PHP

      In this step you will create a test database (DB) with simple "To do list" and configure access to it,
so the Nginx website would be able to query data from the DB and display it.

At the time of this writing, the native MySQL PHP library mysqlnd doesn't
support caching_sha2_authentication, the default authentication method for MySQL 8. We'll need to
create a new user with the mysql_native_password authentication method in order to be able to
connect to the MySQL database from PHP.

We will create a database named damilare_database and a user named damilare_user.

  ## 1. First, connect to the MySQL console using the root account:

      sudo mysql

  ## 2. Create a new database

        CREATE DATABASE `damilare_database`;

  ## Output
      ![33](https://github.com/user-attachments/assets/9798677e-897e-44ae-83c8-cd52c0be84a2)

  ## 3. Create a new user and grant it full access on the database 

      Use the following command

          mysql> CREATE USER 'damilare_user'@'%' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';

      ![34](https://github.com/user-attachments/assets/ea3ac9f8-2c45-4f7e-a755-977bea066c6f)

  ## 4. Grant this user permission over the damilare_database Database:

        mysql> GRANT ALL ON damilare_database .* TO 'damilare_user'@'%';






  



     




    

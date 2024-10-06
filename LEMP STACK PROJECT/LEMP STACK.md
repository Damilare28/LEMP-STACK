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

# Installing php-fpm and php-mysql

  While Apache embeds the PHP interpreter in each request, Nginx requires an external program to handle PHP processing and act as a bridge between the PHP interpreter itself and the web server. This allows for a better overall performance in most PHP-based websites, but it requires additional configuration. You'll need to install php-fpm, which stands for "PHP fastCGI process manager", and tell Nginx to pass PHP requests to this software for processing. Additionally, you'll need php-mysql, a PHP module that allows PHP to communicate with MySQL-based databases. Core PHP packages will automatically be installed as dependencies.
  The two packages can be installed at once:
        sudo apt install php-fpm php-mysql


     




    

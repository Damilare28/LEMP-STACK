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
   
   http://<"Public ip address">:80-- "In place of the <Public-IP-Address> Use the public ip address on the instance page"
   
   Note: If the page is displayed, then the web server is now correctly installed and accessible through your firewall.
![10](https://github.com/user-attachments/assets/1568cae4-8bcc-4918-9d01-3f9354ac1127)




    

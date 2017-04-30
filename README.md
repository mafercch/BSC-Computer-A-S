# INTRODUCTION

The purpose of this project was to carry out the creation of a web page through a few steps delivered in classes by the teacher, in each class we performed different complex but essential steps for the elaboration of the same, using virtual box and the server of ubuntu.
The success of this project was based on the assistance to these classes with the purpose of clarifying the doubts and problems presented in the process of preparing the project.
The project elaborated cost of three steps followed in 4 practical classes of architecture and computer system.

-	DEPLOYMENT OF LOCAL UBUNTU SERVER ON A VIRTUAL MACHINE.
-	DEPLOYMENT OF A LAMP STACK ON YOUR UBUNTU SERVER 
-	CONTENT MANAGEMENT SYSTEM (CMS)

## FIRST STEP

### DEPLOYMENT OF LOCAL UBUNTU SERVER ON A VIRTUAL MACHINE AND CREATIONG OF A GITHUB FREE ACCOUNT.

The Virtual box is a virtual software for x86 / amd64 architectures, through this application you can install additional operating systems, better known as guest systems, this is located inside another operating system called host and each of these has its own virtual environment, this is available for windows, Linux and Mac OS X or other operating systems.
This has the function of creating virtual disk drives where you can install operating systems within the one normally used in our computer being used as if it had actually been installed.
Before explaining a little of the activity elaborated in class, you will find some configuration steps that were used for the Ubuntu server installation. 

 1. Memory Size: 2048mb.
 2.	Virtual Hard Disk.
 3.	VDI.
 4.	dynamically allocated. 
 5.	20gb.
 6.	Select English as the language.
 7.	Not to detect the keyboard layout but select it from the list instead.
 8.	After setup has configured, enter the hostname for your computer.
 9.	create a password that you remember.
 10.	Choose a guided partition and the volume of the entire disk.
 11.	Confirm changes to the disk in the
 12.	subsequent menus.
 13.	Don’t set up a proxy and choose automatic security updates.
 14.	Install the GRUB bootloader and finish the installation.
 
This application and configuration steps were essential to begin the project and carry it out. In the first class was given the first step written in a sheet of paper by our teacher Conor McGinn, this was the installation of Ubuntu server as virtual disk in our computer through its page or his pendrive to facilitate a little this process, it took about a couple of hours and immediately while I finished installing following the steps given, we went to the Github.com page for the elaboration of a free profile where our report will be published and he can see the report through a link that the page elaborated.

GitHub is a platform that uses the Git version system to host projects, the code can be stored publicly for free or privately creating a payment account.

## SECOND STEP

#### DEPLOYMENT OF A LAMP STACK ON YOUR UBUNTU SERVER.

In the second practice classes for the elaboration of the project we had as objective the installation of Apache web-server and MySQL.
a web service is a software interface that describes a set of operations that can be accessed by the network through standardized XML messaging. Uses protocols based on the XML language with the objective of describing an operation to execute or data to interchange with another web service.  
Apache is an open source HTTP web server for Unix platforms (BSD, GNU / Linux, etc.), Microsoft Windows, Macintosh and others, which implements the HTTP / 1.1 protocol and the notion of virtual site.

- Apache Web-server installation.
- MySQL installation.
- Install PHP and Modules.

### APACHE WEB-SERVER INTALLATION

Already having the ubuntu server installed we started in this second step to install the apache web server using the commands written in classes. The steps followed were.

A.	We enter the command below to install the Apache Web Server: sudo apt-get install apache2 apache2-utils.

B.	We want to change our setting so the Apache2 web server will start up at system boot. To do this enter the systemctl enable command. Type the following: sudo systemctl enable apache2.

C.	We also want to start the service now by entering the command: sudo systemctl start apache2.

D.	Check that the apache server is running. To see that our VM is visible from our host. Need to turn off our VM and change the configuration in our virtual network adapter. Go to the setting, then go to the network, choose the advanced option and last part click on port forwarding. After being there we must add a new file called apache with a host post the 80 and then accept.

E.	The last step was to access the default homepage the apache homepage by typing http://localhost:80 into your Browser.
To be all the configurations correctly the page must load and show that it works correctly, however apache is just for simple and basic 
web pages, if we wanted to get modern and complex pages we had to continue with a few more steps.

### MYSQL INSTALLATION

MySQL is an open source Database program. It’s vital for many features of modern websites to maintain databases for purposes such as allowing users to login, saving any user generated input to the website e.g. posts on a forum etc.
To carry out the installation it was necessary to follow the given steps in class.

A.	To install our MySQL database server run the following command: sudo apt-get install mysql-client mysql-server.

B.	Our database is not yet secure. As we are not configuring a website for a production environment then security is of less importance. However, if we should run the following command to see how security would normally be configured: Sudo mysql_secure_installation.

C.	 We can enforce a password strength policy. For a production environment, a strong password is very important, however for our testing environment we can choose the settings which will make our environment easier to get up and running. For most of these settings I would advise selecting No in our testing environment as we’re prioritising convenience over security. If you change the root password make sure you take a note of it. Choose yes to reload privilege tables, so any changes take effect now.

The last part of this practice class consists of making a last installation so that the configuration of the modern and complex page was successful.

### INSTALL PHP AND MODULES.

PHP is an open source server-side scripting language mainly used for web development. It allows web developers to create dynamic, interactive websites.

A.	Enter the following command to install php and the modules we will need for our Content Management System:

## sudo apt-get install php7.0 php7.0-mysql libapache2-mod-php7.0 php7.0-cli php7.0-cgi php7.0-gd 

B.	When the command is finished running we need to test that PHP is working. We will do this by creating a info.php file in our /var/www/html directory. We are going to create that file and open it in text editor Vi (which we used previously) to insert some basic PHP code to test. Type the command:

## sudo vi /var/www/html/info.php 

C. This will open a new file called info.php. Press the i key to enter insert mode and then type the following php code in: 
## <? Php
## Phpinfo();
## ?>

D.	Press ESC when you’re done entering text then enter the command: 
## :wq 
to save your file and close Vi.

After the steps shown above, the page localhost/php.info opened without any problem, since the steps followed were correct, this page contained some configuration information.

## THIRD STEP

In the last step was the installation of the WordPress page for the demonstration in class, this page is intended to show that the previous processes were carried out correctly and effectively.
As we did earlier this step it also had to type some commands on the virtual box and so this could show me a modern and complex page example afterwards.

The commands were:
## wget -c http://wordpress.org/latest.tar.gz
## tar -xzvf latest.tar.gz
## sudo rsync -av wordpress/* /var/www/html/
## sudo chown -R www-data:www-data /var/www/html
## sudo chown -R www-data:www-data /var/www/html

### CREATE A MYSQL DATABASE FOR WORDPRESS 

Before we can run Wordpress we need to set up a MySQL database for it. Enter the following command to open MySQL:
## mysql -u root -p 

With MySQL now open enter the following commands line by line to create your database. Make sure you use a strong and secure password. 
## CREATE DATABASE wp_project; GRANT ALL PRIVILEGES ON wp_project.* TO ‘your_username_here’@’localhost’ IDENTIFIED BY ‘your_chosen_password_here’; 

## FLUSH PRIVILEGES; 

## EXIT; 

We can restart the web server and MySQL service to allow changes to take effect. 

## sudo systemctl restart apache2.service 
## sudo systemctl restart Mysql.Service 

Go to the address http://localhost:80/wp-config-sample.php 

You will be prompted to enter the information about your MySQL database which you created in the previous step.

Immediately when I typed the page http://localhost:80/wp-admin on my browser the WordPress page opened and immediately I set it up and made some adjustments to my liking.

### PROBLEMS PRESENTED DURING THE PROCCESS OF THE PROJECT

The first steps seemed to me very easy and fast, the only thing that I had to write down the user and password because I forgot and therefore I have to install Ubuntu server again and create a new user and password, that is one of the things I would avoid and write my data.

The second time I did it inside the written guide given by the tutor recommended writing the user data and password, but, for not having read carefully and with patience, I had to go back to do the whole installation process. It would be another thing to take into account that is to carefully read every step and recommendation. 

The last part of the installation cost me to finish the process and block me because I could not get good results, other classmates happened the same to them but they looked for information on the internet, to continue with the process while they continued I just stuck in that I could not, but, with the help of other classmates, I could finish my project, which would avoid blocking my mind or stressing me knowing that on the internet we can search for information to solve any type of problem with respect to the subject.

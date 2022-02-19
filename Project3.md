Step 1 - Create a directory named vagrant-vms
  
  Command: mkdir vagrant-vms

Step 2 - Create a directory with the name wordpress to be hosted.
  
  Comman: mkdir wordpress

Step 3 - Change directory to the directory created in step 2
 
 Command: cd wordpress

Step 4 - Create a vagrantfile in the wordpress directory with the vagrant box config gotten from vagrant cloud.
 
 Command: vagrant init <Virtual box link>

  ![IMG_877F7AD4DB88-1](https://user-images.githubusercontent.com/93732510/154818331-2063554f-900c-416e-a87b-219c74332bf0.jpeg)

Step 5 - Use vim editor to modify the vagrantfile configuration. (this is to change IP address from previous website)
  
  Command: vim vagrantfile

Step 6 - Bring up the vm 
 
  Command: vagrant up

  ![IMG_9022](https://user-images.githubusercontent.com/93732510/154818518-2c6148e6-d933-4ca0-8105-835ad7a0092e.jpg)

Step 7 - Now that the vm is running, we can log into it. 
 
  Command: vagrant ssh
  
Step 8 - Change to root user
  
  Command: sudo -i
 
Step 9 - update packages
 
  Command: sudo apt update -y 
  
  ![IMG_9AFA3F211AB9-1](https://user-images.githubusercontent.com/93732510/154818633-7d56c187-a47e-4023-8f61-59590cc556b9.jpeg)

Step 10 - Start to install dependencies
 
 ![IMG_DD96E615DB3D-1](https://user-images.githubusercontent.com/93732510/154818911-a264329d-b32e-41f6-af18-41111017cac7.jpeg)

Step 11 - Create the installation directory and set ownership to user www-data
  
  ![IMG_666CDB2FA06B-1](https://user-images.githubusercontent.com/93732510/154819027-6843bd11-91aa-44db-85a2-d9a89dbeb0f4.jpeg)
  
Step 12 - Configure apache for wordpress using vi editor. 
   
  Command: vi /etc/apache2/sites-available/wordpress.conf
  
  ![IMG_3A53F44049CD-1](https://user-images.githubusercontent.com/93732510/154819114-8003f86e-8d46-42ac-ae2e-26f47c390b4a.jpeg)
  
Step 13 - Next is to enable the site, enable URL rewrite, disable default "it works" page
   
  ![IMG_8CA12FDB3CFF-1](https://user-images.githubusercontent.com/93732510/154819204-c99bc4f4-1058-4777-bd0e-83f42115d72c.jpeg)
 
Step 14 - Reload apache to effect all the changes
    
 Command: sudo service apache2 reload

Step 15 - To host the wordpress, there is need to create and configure a database to store data.
  
  Command: $ sudo mysql -u root; 
            
  mysql> CREATE DATABASE wordpress;
             
  mysql> CREATE USER wordpress@localhost IDENTIFIED BY '<admin123';
               
  mysql> GRANT SELECT,INSERT,UPDATE,DELETE,CREATE,DROP,ALTER
   
    -> ON wordpress.*
   
    -> TO wordpress@localhost;  
  
  mysql> FLUSH PRIVILEGES;

Step 16 - Now we configure wordpress to use the database and set the credentials in the configuration file. Then open vim editor and edit the file as per ubuntu document.
   
  ![IMG_F39377EA6A39-1](https://user-images.githubusercontent.com/93732510/154821854-ffa43494-1f8b-4245-b29a-e2f34ded3df3.jpeg)


Step 17 - Get the IP address using ifcong or IP addr show 

Step 18 - Use the IP address to access wordpress
  
 ![IMG_5DC06CAA231C-1](https://user-images.githubusercontent.com/93732510/154821976-c52424f8-35af-4806-a88e-7bea3991ff34.jpeg)

  

  

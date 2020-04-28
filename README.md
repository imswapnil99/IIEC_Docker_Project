# IIEC_Docker_Project
Under **IIEC-RISE 1.0** Campaign
Successfully completed a Docker Training a week ago.
under a guidance of World Record Holder My Mentor Mr.Vimal Daga sir. 

## Project Explaination:
* Deploying a website/web application in One click.
    * Nextcloud as Webapp.
    * Mysql as Database.
    
## 1. Pre-configurations needed:
**RedHat Enterprise Linux** version 8 inside that docker should be installed and you should know some basic linux command . 

## 2.Image required are:
* Pulling MySQL Image:
  * Use `docker pull mysql:5.7` to download the **mysql version 5.7** image to use as a database server.
* Pulling nextcloud Image:
  * Use `docker pull nextcloud:18.0.4-apache` to download the **nextcloud** Image in which apache server is already preconfigured.
  
## 3. Docker-Compose:
  * Before using Docker-Compose you should install the software. For reference go to this website : https://docs.docker.com/compose/install/
  * You can create and edit this file using vim editor. For that use `vim docker-compose.yml`. Remember the file name should always be **docker-compose.yml**.
 
 ### services:
   * In docker compose we use the term services to rectify which things will run when we start the compose file.
   
### volumes:
   ` docker create volume [volume name]` . 
   * In docker as soon as we terminate an container our whole data inside that container destroyed. But if we want to make our data permanent then we have to use **docker volume**.
### Depends_on and ports:
   * As we know nextcloud needs MySQL database server to store data that's so we need to use **depends_on**. 
   
## 4. Docker-compose up:
   * As per the below mentioned picture use `docker-compose up` to complete the setup.
## 5. Docker-compose start:
   * After using docker compose up whole setup/infrastrure is done .
         * ` docker-compose start `.
## 6. Docker-compose down:
   * We can easily stop the containers using `docker compose down` command.

## THANK'S A LOT VIMAL SIR FOR YOUR GUIDANCE!!!

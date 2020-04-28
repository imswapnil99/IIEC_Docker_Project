# IIEC_Docker_Project
Under **IIEC-RISE 1.0** Campaign
Successfully completed a Docker Training a week ago.
under a guidance of World Record Holder My Mentor Mr.Vimal Daga sir. 

## Project Explaination:
* Deploying a website/web application in One click.
    * Webapp as Nextcloud.
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
   * In docker as soon as we terminate an container our whole data inside that container destroyed. But if we want to make our data permanent then we have to use **docker volume**.` docker create volume [volume name]` . 

### depends_on and ports:
   * As we know nextcloud needs MySQL database server to store there files that's why we are using **depends_on**. Also we know that we have to expose our container(where joomla running) to a specific port otherwise from outside world we will not be able to access our WebApp.
   
## 6. Docker-compose up:
  * As per the below mentioned picture use `docker-compose up` to complete the setup.


## 8. Docker-compose start stop:
   * After using docker compose up now in one click you can stop your whole setup. Just use `docker-compose stop`. Again you want to start the service use `docker compose start`. 

## 9. Docker-compose down:
  * You can easily stop the containers using `docker compose down` command.
## Troubleshooting and Solves:
  #### There might be a possibility that you may face some troubleshoots. As we know in these kinds of automations are depended on many things and suppose any of the dependency might not accurate. Here are some suggestions:
   * After you restart your base OS you will see problem cause previous time you stopped your firewall and after system restart firewall will start again. So before again starting docker-compose you should stop firewall. You can check the status of your firewall using `systemctl status firewalld`. If you want to permanently disable firewall you can use `systemctl disable firewalld`.
   * Next problem might happen after you setup your MySQL you up your docker compose and your joomla might not get the connection with MySQL. It's probably because there are limitations that how much container you can connect with your database server. I don't know anything about database handling but as per my knowledge after setting up the MySQL user and database name run this command `docker rm -f $(docker ps -aq)` . This command will remove all the previous containers. Otherwise you can also use `docker ps -a` to see which container is running on MySQL server and you can remove that particular container using `docker rm (container id)`.
   * Next problem might happen like your joomla is unable to connect to database server. It's probably because your iptables doesn't get updated as soon as you do the previously mentioned action. So final and last solution is that you should at first remove the containers create previously by docker compose and then restart your docker using `systemctl restart docker` and now you just up the docker-compose and it will work fine. 
## Future possibilities:
   ### This whole setup is done in local machine. But exactly same thing we can do in cloud to setup a Joomla WebApp. We can use many cloud services like Google Cloud, Digital Ocean etc. for this.
   

## Lastly Thank you so much Vimal Daga Sir.

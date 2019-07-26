# Linux Server Configuration
 The purpose of this project is to host one of the existing website application on linux-ubuntu server using amazon lightsail and configure database server to protect database from number of attacks.

 ## Quick Installation
 One can access the Website by visiting this URL[here](http://52.62.67.187/catalog).
 However to validate the server code,Install Vagrant[here](https://www.vagrantup.com/downloads.html) and virtual machine[here](https://www.oracle.com/technetwork/server-storage/virtualbox/downloads/index.html).
 Clone this project[here](https://github.com/siloni07/catalog_linux).In Git Bash run the following command to make your virtual machine up and running.

```
cd catalog_linux/
vagrant up
```
Please note it may take sometime for "vagrant up" command to get complete. Now, The system is ready to use. Use _Vagrant ssh_ command afterwards to fastly configure your virtual machine.

## Install
Once vagrant is up and running. Run the following command to access aws server with "grader" as user on port "2200"

```
sudo ssh -i ~/.ssh/grader_key.rsa -p 2200 grader@52.62.67.187
```
Now you have logged in aws server. Website will be located in following directory
```
cd /var/www/catalog/catalog
```
To make server compatible with website,various libraries have been installed - httplib2,sqlalchemy,psycopg2 on virtual environment which can be viewed using following command. 
```
. venv3/bin/activate
```
To protect database from any attack,user "catalogl" has been created for postgresql database "catalog" which can be accessed using following command:
```
sudo su - postgres
psql
```


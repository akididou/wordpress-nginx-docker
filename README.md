# How to start ?

### 1. Change variables ###

First, change variables on files : 
 - .env
 - example.conf
 - default.conf

### 2. Active reverse proxy ###

Put example.conf on your nginx available sites and enable it. 

### 3. Run docker containers ###

Go to your example folder where you clone the project and run it : `docker-compose -f example.yml up -d`

# Files

### example.conf

File configuration for nginx. It's use to reverse proxy from DNS name (example.org) to web server (localhost:NGINX_PORT).

You need to put him on your Nginx available folder : `/etc/nginx/sites-available/example.conf`

**Don't forget to enabled** it with a symbolic link : `ln -s /etc/nginx/sites-available/example.conf /etc/nginx/sites-enabled/example.conf` 

**Don't forget to change variable on it**

### default.conf

File configuration for nginx. It's use to serve Php files needed for wordpress. 

Let it in your example folder, because is directly linked to the container Nginx server

**Don't forget to change variable on it**

### example.yml

Docker-compose file use to create and run all the containers.

To run it you **must need** to go on the **local folder** and execute : 
`docker-compose -f example.yml up -d`

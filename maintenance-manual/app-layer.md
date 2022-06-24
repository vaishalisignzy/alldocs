# App layer

App layer hosts one major service.

1. Indusind-back

The below mentioned details are applicable for both the application servers.

## Indusind-back

```bash
# First we need to see the docker containers running.
# Run the below command to get the list of docker containers running
sudo docker ps

# To get the list of stopped containers also
sudo docker ps -a

# The above commands will give a random number called the docker container's ID

# You can enter into one of the docker containers using below command, replace the
# docker-id with the id you get from the above command.
sudo docker attach <docker-id>

# Reach the indusind directory using the below command
cd /microservices/indusind-back

# start the indusind backend service using the below command
pm2 start . --name indusind-back

# To stop the persist server from this directory
pm2 stop indusind-back

# To start the nginx service on the application server
# First check if it is already running using below commnad
service nginx status

# If it is stopped, you can start using below command
service nginx start

# To restart the nginx service after any configuration changes, run below command
service nginx restart

# to come out of the docker container, you need to press 
ctrl + p & ctrl + q

# To start a stopped docker container, run below command, the docker id should 
# be replaced with the ID you get from the docker ps command.
sudo docker start <docker-id>

# To pull a latest docker image 
docker pull 35.200.158.194/indusind-app-server-16

# Run the below command to start a new docker container. This needs to make 
# sure any of the existing docker containers for a particular docker image isn't
# running. If any containers are running, then they will need to be stopped using
# command mentioned above.
sudo docker run -it --network=host -p 5000:5000 -p 52301:52301 -p 52302:52302-p 27017:27017 -p 52303:52303 -p 443:443 -p 80:80 35.200.158.194/indusind-app-server-16 /bin/bash
```

## Mongo.prv

You should create an entry in the **/etc/hosts** file with name **mongo.prv** and point into the local IP of database server.

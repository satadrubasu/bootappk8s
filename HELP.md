# Getting Started


## Ubuntu Machine Mongod
==========
    If you installed via the package manager, the data directory /var/lib/mongodb and the log directory /var/log/mongodb are created during the installation.

    By default, MongoDB runs using the mongodb user account. If you change the user that runs the MongoDB process, you must also modify the permission to the data and log directories to give this user access to these directories.
  >  chown and chgrp on these two folders  
  
  > sudo systemctl start mongod
  > sudo systemctl status mongod
  > sudo systemctl stop mongod 
  > /var/log/mongodb/mongod.log  
  
  Start a mongosh session on the same host machine as the mongod. You can run mongosh without any command-line options to connect to a mongod that is running on your localhost with default port 27017.  
  > mongosh
  
  
  ## DockerD
   > systemctl status docker.service
   > systemctl restart docker.service
   
  
  ## Stop mongo running on host machine 
   > systemctl restart docker.service  
   
  ## Building the app as container with Dockerfile   
  
    >  docker build -t knote-java .
  
  
  ## Create a docker network for connectio napp container and mongo container
 
    > docker network create knote 
    
  ## Run mongo as a container
   
  ``` 
   docker run \
  --name=mongo \
  --rm \
  --network=knote mongo
  ```

  ## Running the app container 
   
   ```
   docker run \
  --name=knote-java \
  --rm \
  --network=knote \
  -p 8080:8080 \
  -e MONGO_URL=mongodb://mongo:27017/dev \
  knote-java
   ```
 
 ## Stopping containers 
 
  >  docker stop mongo knote-java
  >  docker rm mongo knote-java  
   
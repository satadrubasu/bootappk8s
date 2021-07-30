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
    

# install_mongodb

#!/bin/bash
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6

#Create the /etc/apt/sources.list.d/mongodb-org-3.4.list
echo "deb [ arch=amd64,arm64 ] http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list

#reload the local package database
sudo apt-get update

#Install the latest stable version of MongoDB
sudo apt-get install -y mongodb-org

#verified that mongod restarts automatically at boot:
sudo systemctl enable mongod

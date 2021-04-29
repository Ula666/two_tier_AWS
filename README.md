# two_tier_AWS
- Launch an ec2 intance with correct version of ubuntu
- ssh into the instance
- update
- upgrade
- install nginx
- access nginx page with public IP

`sudo systemctl status nginx` to check nginx status
- copy code from OS to AWS EC2 app with scp command
- go into eng84_dev_env and use command below: 
- `scp -i ~/.ssh/your_pem_file -r app/ ubuntu@ip:~/app/` - to copy OS from the other folder
- `scp -i ~/.ssh/pem_file -r ubuntu@ip~/` to copy one file
- `scp -i ~/.ssh/pem_file -r environment/ ubuntu@ip:~/ `
### to fix permision issue for  
### dos2unix commands
`wget "http://ftp.de.debian.org/debian/pool/main/d/dos2unix/dos2unix_6.0.4-1_amd64.deb"`
`sudo dpkg -i dos2unix_6.0.4-1_amd64.deb`
`dos2unix provision.sh`
- to connect to db > select your db instance from the instance list and click Connect > copy example
- commands in db instance
- `wget -qO - https://www.mongodb.org/static/pgp/server-3.2.asc | sudo apt-key add -`
`echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list`
`sudo apt-get update`
`sudo apt-get install -y mongodb-org=3.2.20 mongodb-org-server=3.2.20 mongodb-org-shell=3.2.20 mongodb-org-mongos=3.2.20 mongodb-org-tools=3.2.20`
`sudo mkdir -p /data/db`
`sudo chown -R mongodb:mongodb /var/lib/mongodb`
`sudo sed -i 's/127.0.0.1/0.0.0.0/g' /etc/mongod.conf`
`sudo systemctl enable mongod`
`sudo service mongod start`
- add in aws db instnace security group> custom tcp > port:27017

- in app instnace:
- `sudo echo "export DB_HOST=mongodb://172.31.43.243:27017/posts" >> ~/.bashrc` 
- `source ~/.bashrc ` to confirm it
- `cat ~/.bashrc     ` to check 

- `cd app`, `cd seeds`, `node seed.js`
- go back to app and `npm start` to check the `ip/posts` page in web browser search bar

* * *

- to run teh provision file `./provishion.sh`
- - sometimes we have to give permission first:
- `sudo chmod +x ./FILENAME.sh`


* [Hello](#hello)  
blebleble


## Hello




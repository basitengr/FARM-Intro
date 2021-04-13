# FARM-Intro
Introducing FARM - FastAPI, React &amp; MongoDB

`apt install -y python3-pip`

`pip3 install -r requirements.txt`

`apt install -y curl`

## import the public GPG key for the latest stable version of MongoDB

https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu

`curl -fsSL https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -`

`apt-key list`

`echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list`

`apt update`

`apt install -y mongodb-org`

To confirm wheter the host has the Ubuntu mongodb package installed, run the following command in a terminal or shell:

`apt list --installed | grep mongo`

If you are unsure which init system your platform uses, run the following command:

`ps --no-headers -o comm 1`

`systemctl start mongod`

`systemctl enable mongod`

https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-20-04

The following command will connect to the database and output its current version, server address, and port. It will also return the result of MongoDB’s internal connectionStatus command:

`mongo --eval 'db.runCommand({ connectionStatus: 1 })'`

```
use admin

db.createUser({
  user: "farmuser",
  pwd: "p@sswOrd",
  roles: [ "root" ]
})
```
Create database
```
db = new Mongo().getDB("farmstackDB")
use farmstackDB
```
 Create user for database
```
db.createUser(
   {
     user: "farmusr",
     pwd: "passwOrd",      // Or  passwordPrompt() to ask for password
     roles: [{ 
      role: "readWrite",
      db: "farmstackDB"
     } ]
   }
)
```

connect to database with username and password

`mongo farmstackDB -u farm -p 'p@sawOrd'`

mongodb connection string
```
export DEBUG_MODE=True
export DB_URL="mongodb+srv://farmusr:passwOrd@localhost/farmstackDB?retryWrites=true&w=majority"
export DB_NAME="farmstackDB"
```


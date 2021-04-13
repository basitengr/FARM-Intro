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

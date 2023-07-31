# Install MongoDB 4.4.18 on Ubuntu 20.04 for Raspberry Pi 4B
According to [this1](https://www.mongodb.com/community/forums/t/core-dump-on-mongodb-4-4-19-on-rpi-4/215223/3) and [this2](https://blog.yucas.net/2023/03/10/how-to-install-mongodb-raspberry-4-working-version/), the MongoDB version that works on Raspberry Pi 4B is up to 4.4.18.
Also, I couldn't find the MongoDB server package on Ubuntu 22.04 for Raspberry Pi 4B, so here are the steps to install MongoDB 4.4.18 on Ubuntu 20.04.

```
# apt update
# apt install wget gnupg software-properties-common ca-certificates lsb-release
# wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | apt-key add -
# echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu $(lsb_release -cs)/mongodb-org/4.4 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-4.4.list
# apt update
# apt install mongodb-org-mongos=4.4.18 mongodb-org-tools=4.4.18 mongodb-org-shell=4.4.18 mongodb-org-database-tools-extra=4.4.18 mongodb-org=4.4.18 mongodb-org-server=4.4.18
```
```
# systemctl enable mongod
# systemctl start mongod
```

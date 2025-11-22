## EC2 User Data Script – NGINX on Ubuntu
``` bash
#!/bin/bash
sudo su -
apt update -y
apt install -y nginx wget unzip

systemctl enable nginx
systemctl start nginx

cd /tmp
wget https://github.com/sairajbasa/frontend-sample-app/raw/main/feane-1.0.0.zip
unzip feane-1.0.0.zip

rm -rf /var/www/html/*
cp -r feane-1.0.0/* /var/www/html

systemctl restart nginx
```

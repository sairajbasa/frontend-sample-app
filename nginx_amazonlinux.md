## 🔥 EC2 User Data Script – NGINX on Amazon Linux or RedHat
``` bash
#!/bin/bash
sudo su -
yum install -y nginx
yum install -y wget unzip

systemctl enable nginx
systemctl start nginx

cd /tmp
wget https://github.com/sairajbasa/frontend-sample-app/raw/main/feane-1.0.0.zip
unzip feane-1.0.0.zip

rm -rf /usr/share/nginx/html/*
cp -r feane-1.0.0/* /usr/share/nginx/html
```

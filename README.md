# 🌐 Frontend Sample – EC2 Deployment Guide

This repository contains the **frontend-sample** application packaged as a ZIP file.  
Follow this guide to deploy the application automatically on an **AWS EC2 instance**.

---

## 🔧 Prerequisites

Before deployment, ensure the following:

1. Launch an **EC2 instance with RedHat / RHEL OS**.
2. Select an instance type (e.g., **t2.micro** for free tier).
3. Security Group must allow:
   - **HTTP (Port 80)** → Required to access the website in a browser
   - **SSH (Port 22)** → Optional but recommended for troubleshooting
4. Assign a **Public IPv4 address** to the EC2 instance.
5. Add the deployment shell script in **EC2 → Advanced Details → User Data**.

---

## 🚀 EC2 User Data – Deployment Script

Paste the script below in **User Data** during EC2 launch:

```bash
#!/bin/bash
sudo su -
yum install -y httpd
yum install -y wget
wget https://github.com/sairajbasa/frontend-sample-app/raw/main/feane-1.0.0.zip
yum install -y unzip
unzip feane-1.0.0.zip
cp -r feane-1.0.0/* /var/www/html
systemctl enable httpd
systemctl start httpd
```

📌 What This Script Does
Step	Action
1	Switch to root user
2	Installs Apache HTTP Web Server
3	Installs wget tool for downloading files
4	Downloads the frontend ZIP file from GitHub
5	Installs unzip for ZIP extraction
6	Extracts the downloaded ZIP file
7	Copies website files to /var/www/html
8	Enables automatic startup for Apache
9	Starts Apache service

🌍 Accessing Your Frontend
After the instance is launched and running:

Go to your web browser

Enter:

cpp
Copy code
```bash
http://<EC2-PUBLIC-IP>
```
You should now see the Frontend Sample Website hosted from your EC2 instance.

📝 Repository Structure
File	Description
feane-1.0.0.zip	Frontend sample application archive
README.md	Deployment documentation

🙌 Support
If you face any issue or want automation support (deploy.sh file or CI/CD), feel free to raise an Issue in this repository.

Happy Deploying! 🚀

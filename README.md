## 🚀 Steps to Deploy the Frontend Sample Application on AWS EC2
1️⃣ Launch an EC2 Instance

Choose Amazon Linux 2 or Ubuntu

Select t2.micro (Free Tier eligible)

Allow HTTP (Port 80) in the security group

2️⃣ Install a Web Server

Install Apache HTTPD (on Amazon Linux) or Apache2 (on Ubuntu)

Enable and start the web server service

3️⃣ Download the ZIP File from GitHub

Navigate to the web server's document root directory

Download the ZIP file from this repository to the server

4️⃣ Extract the ZIP File

Unzip the downloaded file into the web server directory

Ensure that all HTML pages, CSS, JS, images, and fonts are extracted correctly

5️⃣ Verify File Permissions

Make sure the web server can read and serve the files

6️⃣ Access the Application

Open the EC2 Public IP address in a web browser

The homepage should load successfully

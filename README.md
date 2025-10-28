# elevate-lab-6
# Apache HTML Website on AWS EC2

## 🖥️ Setup Overview

- **Platform:** AWS EC2  
- **Web Server:** Apache (`httpd`)  
- **Content:** Static HTML pages (`index.html`, `about.html`)  
- **Access:** Public via EC2 IP or DNS  
- **Public IP:** http://43.204.218.192
---

## 🚀 Deployment Steps

### **1. Launch EC2 Instance**
- Select **Amazon Linux**
- Choose **t2.micro** (Free Tier eligible)
- Configure **Security Group**:
  - Allow **SSH (port 22)** for terminal access  
  - Allow **HTTP (port 80)** for web access  

---

### **2. Connect to EC2 via SSH**
```bash
ssh -i "kanmani.pem" ec2-user@ec2-43-204-218-192.ap-south-1.compute.amazonaws.com

---
3. Install Apache 
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd

4. Create HTML Files
index.html
<!DOCTYPE html>
<html>
<head>
  <title>My Apache EC2 Website</title>
</head>
<body>
  <h1>Welcome to My EC2 Website!</h1>
  <p>This is a dynamic site served by Apache on AWS EC2.</p>
  <a href="about.html">
    <button style="padding: 10px 20px;">Go to About Page</button>
  </a>
</body>
</html>

about.html
<!DOCTYPE html>
<html>
<head>
  <title>About</title>
</head>
<body>
  <h1>About Page</h1>
  <p>This is the About section of my EC2 website.</p>
  <a href="index.html">Back to Home</a>
</body>
</html>

5. Save Files
cd /var/www/html
sudo nano index.html
sudo nano about.html

6. Access Website

Public IP: http://43.204.218.192

Public DNS: http://ec2-43-204-218-192.ap-south-1.compute.amazonaws.com


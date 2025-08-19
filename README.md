# 🚀 RHA Day Workshop – Hosting Websites on Apache & WordPress with Docker

Welcome to **Red Hat Academy Day (RHA Day)**!  
In this workshop, we will do **two practicals**:  

1. Hosting a static website using **Apache2 (httpd)**  
2. Hosting a **WordPress & MYSQL site using Docker**

---

## ⚙️ Prerequisites
- KillerKoda Ubuntu Environment (or any Linux VM with `apt`) 
- Killerkoda Link - https://killercoda.com/playgrounds/scenario/ubuntu 
- Internet connection  
- Basic Linux knowledge (commands, sudo)  

---

## 📝 Part 1: Hosting a Website with Apache HTTPD

### 1. Install Apache
```bash
sudo apt install apache2 -y
```
👉 Installs the Apache web server.  

### 2. Start & Enable Apache
```bash
sudo systemctl restart apache2
sudo systemctl enable --now apache2
```
👉 Ensures Apache starts now & automatically after reboot.  

### 3. Create a Custom Web Page
```bash
echo "<h1>Welcome to RHA Day</h1>" > /var/www/html/index.html
```
👉 Replaces the default page with your custom message.  

### 4. Test the Website
```bash
curl http://localhost
```
👉 You should see your custom HTML.  
Open browser → `http://<your-killerkoda-ip>`  

---

## 📝 Part 2: Hosting WordPress using Docker

### 1. Install Docker
```bash
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
```
👉 Installs Docker + Docker Compose and enables it.  

---

### 2. Run MySQL Container
```bash
docker run --name wp-db \
-e MYSQL_ROOT_PASSWORD=rootpass \
-e MYSQL_DATABASE=wordpress \
-e MYSQL_USER=wpuser \
-e MYSQL_PASSWORD=wppass \
-d mysql:5.7
```
👉 Creates a MySQL DB container with WordPress credentials.  

---

### 3. Run WordPress Container
```bash
docker run --name wp-site \
-p 8080:80 \
-e WORDPRESS_DB_HOST=wp-db:3306 \
-e WORDPRESS_DB_USER=wpuser \
-e WORDPRESS_DB_PASSWORD=wppass \
-e WORDPRESS_DB_NAME=wordpress \
--link wp-db:mysql \
-d wordpress
```
👉 Runs WordPress container connected to MySQL.  

---

### 4. Access WordPress
Open in browser:  
```
http://<your-killerkoda-ip>:8080
```
👉 You should land directly on **WordPress setup (site title, admin user)** – no DB setup screen!
use your Own Theme and customize your wordpress Site 🎉  

---

## ✅ Wrap-Up
- Apache shows how to host a **basic website**.  
- Docker shows how to host **dynamic apps (WordPress)** easily.  
- This is the first step toward **DevOps & Cloud technologies**.  

---

✍️ **Trainer:** Gaurav Sidharth Bharane  
🎓 *Red Hat Academy Day Workshop*  

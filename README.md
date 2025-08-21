# 🚀 RHA Day Workshop – Hosting Websites & Games with Docker

Welcome to **Red Hat Academy Day (RHA Day)**!  
In this workshop, we will do **two practicals**:  

1. Hosting a static website using **Apache2**  
2. Hosting a **Game using Docker Container**

---

## ⚙️ Prerequisites
- KodeKloud Free Labs (Ubuntu environment)  
- Internet connection  
- Basic Linux knowledge (commands, sudo)  

---

## 📝 Part 1: Hosting a Website with Apache2

### 1. Install Apache
```bash
sudo apt install apache2  -y
```
👉 Installs the Apache web server.  

### 2. Start & Enable Apache
```bash
sudo systemctl start apache2
sudo systemctl enable apache2
```
👉 Ensures Apache starts now & automatically after reboot.  

### 3. Create a Custom Web Page
```bash
echo "<h1>Welcome to RHA Day - Hosted on Apache2!</h1>" | sudo tee /var/www/html/index.html
```
👉 Replaces the default page with your custom message.  

### 4. Test the Website
```bash
curl http://localhost
```
👉 You should see your custom HTML.  
Open browser → `http://<your-lab-ip>`  

---

## 📝 Part 2: Hosting a Game with Docker

### 1. Install Docker
```bash
sudo apt update
sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
```
👉 Installs Docker and enables it.  

---

### 2. Run the Game Container
```bash
docker run -d -p 8080:80 gauravbharane1839/jumpyfly
```
👉 Runs the JumpyFly game inside a Docker container.  

---

### 3. Access the Game
Open in browser:  
```
http://<your-lab-ip>:8080
```
👉 Play the **JumpyFly Game** 🎮 hosted in Docker.  

---

## ✅ Wrap-Up
- Apache shows how to host a **basic static website**.  
- Docker shows how to **package and deploy applications** easily (in this case, a game 🎮).  
- This is the foundation for **DevOps & Cloud technologies**.  

---

✍️ **Trainer:** Gaurav Sidharth Bharane  
🎓 *Red Hat Academy Day Workshop*  

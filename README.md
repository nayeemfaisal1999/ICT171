# FaisalPortfolio – Cloud Server Project 🌐

**By:** Nayeem Faisal  
**Unit:** ICT171 – Introduction to Server Environments and Architectures  
**Student ID:** 35162293  

---

## 🌍 Project Overview
FaisalPortfolio is a personal showcase site hosted on a manually configured Ubuntu server (DigitalOcean).  
I built the front-end with HTML, CSS and JavaScript, served it with Apache, and locked it down with HTTPS via Certbot.

---

## 🛠 Tech Stack
- Ubuntu 22.04 LTS (IaaS on DigitalOcean)  
- Apache 2.4 Web Server  
- SSL/TLS with Let’s Encrypt (Certbot)  
- HTML / CSS / JS front-end  
- Bash backup script + optional cron job  
- GitHub for version control  

---
## Domain & IP

- Domain: https://35162293.com  
- IP Address: 170.64.252.201
## 📁 Files Included
- `site/` – full website source  
- `scripts/backup-site.sh` – compresses `/var/www/html` into `/root/backups` with a timestamp  
- `docs/` – screenshots and step-by-step build notes  
- `README.md` – this file  

---

## 🚀 Quick Deploy Steps
```bash
# 1  Install Apache
sudo apt update && sudo apt install apache2 -y

# 2  Copy website files
sudo rsync -av site/ /var/www/html/

# 3  Fix ownership (optional)
sudo chown -R www-data:www-data /var/www/html

# 4  Enable HTTPS (see docs/ssl.md for full commands)
sudo apt install certbot python3-certbot-apache -y
sudo certbot --apache

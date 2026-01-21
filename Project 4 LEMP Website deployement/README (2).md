# LEMP Server Setup on Ubuntu

This guide explains how to install and launch a simple LEMP server (Linux, Nginx, MySQL, PHP) on Ubuntu, and create HTML and PHP test pages.

## Steps

### 1. Update Packages
```bash
sudo apt update
```

### 2. Install Nginx, MySQL, PHP, and PHP-FPM
```bash
sudo apt install nginx mysql-server php php8.3-fpm -y
```

### 3. Start Services
```bash
sudo systemctl start nginx mysql php8.3-fpm
```

### 4. Enable Services to Start at Boot
```bash
sudo systemctl enable nginx mysql php8.3-fpm
```

### 5. Check Service Status
```bash
sudo systemctl status nginx mysql php8.3-fpm
```
Press `q` to exit the status view.

### 6. Navigate to Web Directory
```bash
cd /var/www/html
```

### 7. Create HTML Test Page
```bash
echo "<h1>This is my LEMP Server on Ubuntu</h1><p>This is my first website deployment</p>" | sudo tee index.html
```

### 8. Create PHP Test Page
```bash
echo "<?php phpinfo(); ?>" | sudo tee index.php
```

### 9. Open in Browser
Replace `YOUR_SERVER_IP` with your server’s public IP:

- HTML page:  
http://YOUR_SERVER_IP/index.html

- PHP page:  
http://YOUR_SERVER_IP/index.php

## Notes
- Ensure that your firewall allows HTTP traffic.
- For production, secure MySQL and configure Nginx properly.

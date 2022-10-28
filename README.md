# Set-Up-a-Node.js-Application
-------------------------------

## Step 1 — Installing Node.js

### cd ~
### curl -sL https://deb.nodesource.com/setup_14.x | sudo bash -
### sudo apt -y install nodejs
### sudo bash nodesource_setup.sh
### sudo apt install nodejs
### nodejs -v
### sudo apt install build-essential


## Step 2 — Installing PM2

### sudo npm install pm2@latest -g
### pm2 start hello.js
### pm2 startup systemd
### sudo env PATH=$PATH:/usr/bin /usr/lib/node_modules/pm2/bin/pm2 startup systemd -u ibrahim --hp /home/ibrahim
### pm2 save
### sudo systemctl start pm2-ibrahim
### systemctl status pm2-ibrahim
### pm2 stop app_name_or_id
### pm2 restart app_name_or_id
### pm2 info app_name
### pm2 monit

## Step 3 — Setting Up Nginx as a Reverse Proxy Server

### sudo nano /etc/nginx/sites-available/example.com
### "/etc/nginx/sites-available/example.com"
###  <pre> server {
###  ...
###    location / {
###         proxy_pass http://localhost:3000;
###         proxy_http_version 1.1;
###         proxy_set_header Upgrade $http_upgrade;
###         proxy_set_header Connection 'upgrade';
###         proxy_set_header Host $host;
###        proxy_cache_bypass $http_upgrade;
###     }
###  ...
###  } </pre>
### sudo nginx -t
### sudo systemctl restart nginx



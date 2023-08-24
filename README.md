# How-To-Setup-a-Reverse-Proxy-with-IP-and-Port
How To Setup a Reverse Proxy with IP and Port

------------------- For Apache WebServer ------------
sudo apt update
sudo apt install apache2
sudo a2enmod proxy
sudo a2enmod proxy_http
sudo systemctl restart apache2

sudo nano /etc/apache2/sites-available/frontend.dollorinfotech.com.conf

paste the content
<VirtualHost *:80>
    ServerName frontend.dollorinfotech.com

    ProxyPreserveHost On
    ProxyPass / http://38.242.236.173:8080/
    ProxyPassReverse / http://38.242.236.173:8080/
</VirtualHost>

sudo a2ensite frontend.dollorinfotech.com.conf

sudo apache2ctl configtest

sudo systemctl restart apache2

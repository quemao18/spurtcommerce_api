#node version 10.x
typescript global
sudo apt-get install graphicsmagick
sudo apt-get install gm -g
sudo npm i typescript@3.8.3 -g 

#USE NGINX proxy_pass 

server {
    
    listen 443 ssl;

    server_name example.com;

    ssl_certificate /etc/letsencrypt/live/example.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/example.com/privkey.pem;

    location /api/ {
            proxy_pass http://example.com:8000/api/;
    }
}


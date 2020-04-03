        2  cd fbmarketing/
        3  sudo npm install -g pm2
        4  npm start
        5  netstat -lnp
        6  kill 15568
        7  netstat -lnp
        8  npm start
        9  pm2 start server.js
       10  ufw status
       11  sudo ufw status
       12  sudo ufw enable
       13  sudo ufw allow ssh
       14  ufw status
       15  sudo ufw status
       16  sudo ufw allow http
       17  sudo ufw allow https
       18  sudo ufw status
       19  sudo apt install nginx
       20  sudo nano /etc/nginx/sites-available/default
       21  sudo nginx -t
       22  sudo service nginx restart
       
       
       
           server_name yourdomain.com www.yourdomain.com;

              location / {
                  proxy_pass http://localhost:5000; #whatever port your app runs on
                  proxy_http_version 1.1;
                  proxy_set_header Upgrade $http_upgrade;
                  proxy_set_header Connection 'upgrade';
                  proxy_set_header Host $host;
                  proxy_cache_bypass $http_upgrade;
              }

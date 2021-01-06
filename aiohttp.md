`https://justin.duch.me/post/aiohttp_deployment_guide/`



        server {
            listen 80;
            server_name 35.239.116.94;
            client_max_body_size 4G;

            location / { 
                try_files $uri @proxy_to_app;
            }

            location @proxy_to_app {
                include proxy_params;
                proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
                proxy_set_header X-Forwarded-Proto $scheme;
                proxy_set_header Host $http_host;
                proxy_redirect off;
                proxy_pass http://unix:/home/data-science/main.sock;
            }
        }

        [Unit]
        Description=Gunicorn instance to serve myapp
        After=network.target

        [Service]
        User=root
        Group=www-data
        WorkingDirectory=/home/data-science
        Environment="PATH=/home/data-science/env/bin"
        ExecStart=/home/data-science/env/bin/gunicorn main:app --bind unix:main.sock --worker-class aiohttp.GunicornWebWorker

        [Install]
        WantedBy=multi-user.target

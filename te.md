## Login credential to server:

1. ssh eric@128.199.133.72
2. goatpac123!


## Make sure that you have all env variables set. If not add belows

    export DB_NAME=defaultdb
    export PGPASSWORD=vc256g25qe1rouuh
    export PGUSER=doadmin
    export PGHOST=db-postgresql-nyc1-49094-do-user-6105241-0.a.db.ondigitalocean.com
    export PGPORT=25060
    export EMAIL_BACKEND=django.core.mail.backends.smtp.EmailBackend
    export EMAIL_HOST=mail.codefolio.org
    export EMAIL_HOST_USER=activation@codefolio.org
    export EMAIL_HOST_PASSWORD=C0def0lio@098
    export DEFAULT_FROM_EMAIL=activation@codefolio.org
    export ACTIVATION_URL=http://dev.eligibilitycheckr.com.ng/active-account
    export API_URL=http://dev.eligibilitycheckr.com.ng/api/


check docker containers `docker ps`
remove any docker image `docker rm image_id --force`

build docker image backend `docker-compose up --build`
run docker container backend `docker-compose up -d`

### Note: Do these inside root folder.

build docker image frontend `docker build -t eligibilitycheckrdevelop_ui_new .
run docker container frontend `docker run -dit --network trisiki_dev -p 3000:3000 eligibilitycheckrdevelop_ui_new

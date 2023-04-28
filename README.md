# docker-laravel-apache

======== Run docker
docker compose up -d | down
docker image ls
docker exec -it [container name] bash
===import sql data into mysql docker
docker exec -i [mysql_container_name] mysql -u[username] -p[password] [DB name] < [path/to/sql/file]
======= If source miss file sessions,views,cache
cd storage/ 
mkdir -p framework/{sessions,views,cache}
chmod -R 775 framework 
chown -R www-data:www-data framework
======= How to configure a development environment with live-reload enabled
Add it:
    volumes:
      - type: bind
        source: /:/
        target: /var/www/html

docker compose up --build

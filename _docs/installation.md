## INSTALLATION ##

### Configure Host ###

- sudo gedit /etc/hosts
- 127.0.0.1	pfed.local
- save

### Configure Laradock ###
- cd laradock

### Configure Workspace Container ###

- sudo docker-compose exec workspace bash (now you are inside the container)
- php artisan storage:link
- php artisan lu:user
- php artisan lu:create-areas
- chown -R laradock:laradock /var/www/
- exit (from the container)

### Run Docker ###
- sudo docker-compose up -d apache2 mysql phpmyadmin redis workspace 

### Access Website ###

- go to http://pfed.local

## NOTES ##

**If you change the .env file in laradock folder:**

- Rebuild the container: docker-compose build apache2

- Restart the containers: docker-compose up

**If you see the folder content inside the URL:**
- Maybe you need to configure virtual host of [laradock_folder]/apache2/sites/default.apache.conf


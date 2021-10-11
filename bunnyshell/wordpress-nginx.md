# Wordpress deployment on nginx

## Creating the virtual machine

1. Create a virtual machine
2. Select Web Server Type

```
nginx
```

1. Select programming language

```
PHP
```

1. Select Database

```
MySQL
```

1. Select Location - the one closest to your users

```
Frankfurt
```

1. Select the operating system

```
Ubuntu
```

1. Select Plan

```
1 cpu / 1gb
```

## Creating the application

1. Create application and choose the virtual machine you have previously created
2. Choose the Wordpress application from the list
3. Deploy
4. Login into the wordpress admin
5. Install All-in-One WP Migration

```
Plugins > Add New > Search: All-in-One WP Migration
```

1. On the origin website go to Export and download the archive
2. On the bunnyshell wordpress instance go to Import
3. We need to change the max upload size
4. SSH into the machine
5. Locate the php.ini file

```
find /etc/ -type f -name php.ini
```

/etc/php/7.4/fpm/php.ini

* Edit the php settings

```
sudo nano /etc/php/7.4/fpm/php.ini
```

* Search for the following properties and update them

```
php_value upload_max_filesize 2048M
php_value post_max_size 2048M
php_value memory_limit 256M
php_value max_execution_time 6000
php_value max_input_time -1
```

1. Increase the nginix client_max_body_size

Open the file

```
sudo nano /etc/nginx/nginx.conf
```

Search for `client_max_body_size` property and update it to `2048m`

1. Restart nginix

```
sudo systemctl restart nginx
```

1. Restart php-fpm/php

```
sudo service php7.4-fpm restart
```

1. Upload the wordpress archive

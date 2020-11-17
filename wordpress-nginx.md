# Wordpress deployment on nginx

##  Creating the virtual machine
1. Create a virtual machine

2. Select Web Server Type

```
nginx
```

3. Select programming language

```
PHP
```

4. Select Database

```
MySQL
```

5. Select Location - the one closest to your users

```
Frankfurt
```

6. Select the operating system

Ubuntu

7. Select Plan

```
1 cpu / 1gb
```

## Creating the application

8. Create application

- choose the virtual machine you have previously created

9. Choose the application

Wordpress

10. Deploy

11. Login into the wordpress admin

12. Install All-in-One WP Migration

```
Plugins > Add New > Search: All-in-One WP Migration
```
13. Go to Import

14. We need to change the max upload size

- SSH into the machine

- Locate the php.ini file

```
find /etc/ -type f -name php.ini
```

/etc/php/7.4/fpm/php.ini


- Edit the php settings

```
sudo nano /etc/php/7.4/fpm/php.ini
```

- Search for the following properties and update them

```
php_value upload_max_filesize 2048M
php_value post_max_size 2048M
php_value memory_limit 256M
php_value max_execution_time 6000
php_value max_input_time -1
```

15. Increase the nginix client_max_body_size

Open the file
```
sudo nano /etc/nginx/nginx.conf
```

Search for ```client_max_body_size``` property and update it to ```2048m```


16. Restart nginix

```
sudo systemctl restart nginx
```

17. Restart php-fpm/php

```
sudo service php7.4-fpm restart
```

18. Upload the wordpress archive

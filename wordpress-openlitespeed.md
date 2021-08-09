# Wordpress deployment on openlitespeed

Wordpress deployment on openlitespeed

## Creating the virtual machine

1. Create a virtual machine
2. Select Web Server Type

```text
openlitespeed
```

1. Select programming language

```text
PHP
```

1. Select Database

   ```text
   MySQL
   ```

2. Select Location - the one closest to your users

```text
Frankfurt
```

1. Select the operating system

```text
Ubuntu
```

1. Select Plan

   ```text
   1 cpu / 1gb
   ```

2. Create application and choose the virtual machine you have previously created
3. Choose the Wordpress application from the list
4. Deploy
5. Login into the wordpress admin
6. Install All-in-One WP Migration

```text
Plugins > Add New > Search: All-in-One WP Migration
```

1. On the origin website go to Export and download the archive
2. On the bunnyshell wordpress instance go to Import
3. Change the php settings to increase the maximum upload size
4. SSH into the machine
5. Locate the php.ini file

```text
find /usr/local/lsws -type f -name php.ini
```

* Edit the file

```text
sudo nano /usr/local/lsws/lsphp74/etc/php/7.4/litespeed/php.ini
```

* Update the following properties

```text
php_value upload_max_filesize 2048M 
php_value post_max_size 2048M 
php_value max_execution_time 6000 
php_value max_input_time -1
```

1. Restart openlitespeed

```text
sudo /usr/local/lsws/bin/lswsctrl restart
```

1. Upload the wordpress archive
2. Make sure you enable the ListSpeed Cache plugin

## SSL Checks

Test redirect on http2

```text
curl --http2 -vI http://
```

Test https

```text
curl --http2 -vI https://
```

## HTTPS Redirect

Add a .htaccess file with the following content

```text
rewriteCond %{HTTPS} !on
rewriteCond %{HTTP:X-Forwarded-Proto} !https
rewriteRule ^(.*)$ https://%{SERVER_NAME}%{REQUEST_URI} [R,L]
```

Restart OpenLiteSpeed

```text
sudo systemctl restart lsws
```

## Let's encrypt auto renewal

Edit /etc/letsencrypt/cli.ini

```text
renew-hook systemctl restart lsws
```


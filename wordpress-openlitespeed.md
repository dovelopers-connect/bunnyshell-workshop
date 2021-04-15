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

php\_value upload\_max\_filesize 2048M php\_value post\_max\_size 2048M php\_value max\_execution\_time 6000 php\_value max\_input\_time -1

1. Restart openlitespeed

```text
sudo /usr/local/lsws/bin/lswsctrl restart
```

1. Upload the wordpress archive
2. Make sure you enable the ListSpeed Cache plugin


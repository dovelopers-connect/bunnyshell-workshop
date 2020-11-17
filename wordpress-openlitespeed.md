Wordpress deployment on openlitespeed

## Creating the virtual machine

1. Create a virtual machine

2. Select Web Server Type

```
openlitespeed
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

```
Ubuntu
```
7. Select Plan
```
1 cpu / 1gb
```
8. Create application and choose the virtual machine you have previously created

9. Choose the Wordpress application from the list

10. Deploy

11. Login into the wordpress admin

12. Install All-in-One WP Migration

```
Plugins > Add New > Search: All-in-One WP Migration
```

13. On the origin website go to Export and download the archive

14. On the bunnyshell wordpress instance go to Import

15. Change the php settings to increase the maximum upload size

- SSH into the machine

- Locate the php.ini file

```
find /usr/local/lsws -type f -name php.ini
```

- Edit the file

```
sudo nano /usr/local/lsws/lsphp74/etc/php/7.4/litespeed/php.ini
```

- Update the following properties

php_value upload_max_filesize 2048M
php_value post_max_size 2048M
php_value max_execution_time 6000
php_value max_input_time -1


16. Restart openlitespeed

```
sudo /usr/local/lsws/bin/lswsctrl restart
```

17. Upload the wordpress archive

18. Make sure you enable the ListSpeed Cache plugin

# e2pv
Listen to Enecsys Gateway posts and sends data to PVOutput

# Setup
Edit the configuration file config.php. 
```php
<?php
define('IDCOUNT', N);
define('APIKEY', 'hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh');
define('SYSTEMID', 'NNNNNN');
?>
```
IDCount needs to be set to the number of inverters you have. APIKEY and
SYSTEMID correspond to your PVOutput api key and System ID.

# Optional MySQL support
php needs to be installed with the mysqli extension enabled.

Create a database and define a table:

```MySQL
CREATE TABLE enecsys (
  ts TIMESTAMP NOT NULL,
  id INT NOT NULL,
  wh INT NOT NULL,
  dcpower INT NOT NULL,
  dccurrent float NOT NULL,
  efficiency float NOT NULL,
  acfreq INT NOT NULL,
  acvolt INT NOT NULL,
  KEY (ts, id)
);
````

You need to set the MYSQL defines in config.php, for example:

```php
define('MYSQLHOST', 'localhost');
define('MYSQLUSER', 'myuser');
define('MYSQLPASSWORD', 'mypw');
define('MYSQLDB', 'mydbname');
define('MYSQLPORT', '3306');
```

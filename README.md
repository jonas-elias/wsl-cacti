# CACTI

Cacti is a robust performance and fault operation frame and a frontend to RRDTool- a Time Series Database( TSDB). It stores all of the necessary information to produce performance operation Graphs in either MariaDB or MySQL, and also leverages its colorful Data Collectors to colonize RRDTool grounded TSDB with that performance data.

Cacti is additionally a LAMP stack Web Application. The term LAMP originally stood for Linux, Apache, MySQL and PHP but over the years the term has evolved. Cacti is now additionally supported on Windows, it has the ability to use Nginx or IIS as its Web Server, and MariaDB is now the default database on various Linux platforms. The key conception of the LAMP stack continues to be consistent. Structural information is stored in the relational database, Time Series information is stored in RRDTool's Round Robin Archives (RRA), and the Web Web page is ultimately guided by PHP.

## Installation In WSL

Update the repository with *apt*
```bash
sudo apt update
```

Install *apache2* && *MariaDB* && lib *php-mysql*
```bash
sudo apt install -y apache2 mariadb-server mariadb-client php-mysql libapache2-mod-php
```

Extensions for operation **php <--> cacti**
```bash
sudo apt install -y php-xml php-ldap php-mbstring php-gd php-gmp
```

Install the SNMP and RRDtool on the server in case you want to monitor the Cacti server as well
```bash
sudo apt install -y snmp php-snmp rrdtool librrds-perl
```

For better performances... Edit the configuration file:
```
sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf
```
```
collation-server = utf8mb4_unicode_ci
max_heap_table_size = 128M
tmp_table_size = 64M
join_buffer_size = 64M
innodb_file_format = Barracuda
innodb_large_prefix = 1
innodb_buffer_pool_size = 512M
innodb_flush_log_at_timeout = 3
innodb_read_io_threads = 32
innodb_write_io_threads = 16
innodb_io_capacity = 5000
innodb_io_capacity_max = 10000
```

Set a timezone in php.ini (in apache2 and php.ini)
```
sudo nano /etc/php/7.2/apache2/php.ini

```
**AND**
```
sudo nano /etc/php/7.2/cli/php.ini
```
**TO**
```
date.timezone = America/Sao_Paulo
memory_limit = 512M
max_execution_time = 60
```

Restart the MariaDB
```
sudo systemctl restart mariadb
```

## Create the Dabase

Log in MariaDB with:
```
sudo mysql -u root -p
```

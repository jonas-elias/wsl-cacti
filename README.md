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

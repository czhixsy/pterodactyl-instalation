# Pterodactyl Instalation 
Easy Panel, Wings and Daemon Installation!

# About Pterodactyl 

Pterodactyl® is a free, open-source game server management panel built with PHP, React, and Go. Designed with security in mind, Pterodactyl runs all game servers in isolated Docker containers while exposing a beautiful and intuitive UI to end users.

# Supported OS Systems

- Operating System  -  Version  - Supported - Notes

- Ubuntu            - 20.04, 22.04  ✅ - Documentation written assuming Ubuntu 20.04 as the base OS. | MariaDB can be installed on Ubuntu 22.04 without the repo setup script.
- CentOS             - 7, 8 ✅ - Extra repos are required. | 	Note that CentOS 8 is EOL. Use Rocky or Alma Linux.
- Debian	     - 10, 11 ✅
  
# Depedency Installation 

- PHP 8.0 or 8.1 (recommended) with the following extensions: cli, openssl, gd, mysql, PDO, mbstring, tokenizer, bcmath, xml or dom, curl, zip, and fpm if you are planning to use NGINX.
- MySQL 5.7.22 and higher (MySQL 8 recommended) or MariaDB 10.2 and higher.
- Redis (redis-server)
- A webserver (Apache, NGINX, Caddy, etc.)
- curl
- tar
- unzip
- git
- composer v2
- #Example Depend

# Example Dependency Installation

- The commands below are simply an example of how you might install these dependencies. Please consult with your operating system's package manager to determine the correct packages to install.

# Add "add-apt-repository" command
apt -y install software-properties-common curl apt-transport-https ca-certificates gnupg

# Add additional repositories for PHP, Redis, and MariaDB
LC_ALL=C.UTF-8 add-apt-repository -y ppa:ondrej/php

# Add Redis official APT repository
curl -fsSL https://packages.redis.io/gpg | sudo gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/redis.list

# MariaDB repo setup script can be skipped on Ubuntu 22.04
curl -sS https://downloads.mariadb.com/MariaDB/mariadb_repo_setup | sudo bash

# Update repositories list
apt update

# Install Dependencies
apt -y install php8.1 php8.1-{common,cli,gd,mysql,mbstring,bcmath,xml,fpm,curl,zip} mariadb-server nginx tar unzip git redis-server

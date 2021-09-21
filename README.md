### Install Docker-CE and Docker Compose (Only for CentOS 7)

```
yum update -y
yum install yum-utils device-mapper-persistent-data lvm2 git -y
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
yum install docker-ce -y
systemctl start docker
systemctl enable docker

curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose
chmod +x /usr/bin/docker-compose


# nginx-phpfpm74
nginx and php-fpm74 with single container

# nginx-php-fpm


### Versions/tags

|  `software`  |      `version`      |
| :----------: | :-----------------: |
| `nginx`      |     `1.19.10`       |
|    `php`     |      `7.4.23`       |
|  `php-fpm`   | `7.3.22 (fpm-fcgi)` |
|   `mysql`    |      `5.7.22`       |

<br>

# Project

```bash
$ cd /root/
$ git clone https://github.com/neir-bohara/nginx-phpfpm74.git 
$ cd nginx-phpfpm74
$ docker-compose up -d

<br>

# PHP Commands
#Inside container
```bash
$ composer install
$ php artisan key:generate
$ php artisan config:cache
$ php artisan migrate
```
<br>

# Mysql Commands

```sql
$ mysql -u root -p
mysql> show databases;
mysql> create database laravel;
mysql> GRANT ALL ON laravel.* TO 'laraveluser'@'%' IDENTIFIED BY 'your_laravel_db_password';
mysql> FLUSH PRIVILEGES;
```

You can browse `http://serverip:8888`.

<br>

# Output

![Alt text](Laravel.png?raw=true "Laravel")


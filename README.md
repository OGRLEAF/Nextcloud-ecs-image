# Nextcloud-ecs-image #
用于在阿里云ECS上快速部署功能完好的Nextcloud

# 简介 #

本镜像包含以下内容
* Ubuntu 16.04.2 LTS x86_64
* Apache 2.4.18
* PHP 7.0.18
* MySQL 5.7.18
* Docker 1.12.6(用于运行Collbora Online)
* Nextcloud 12.0.1

## 配置文件位置 ##
为了方便部署，我尽可能地保留了默认配置。
### Apache ###
* 主配置文件 /etc/apache2/apache.conf
* 虚拟主机1（运行Nextcloud）：/etc/apache2/sites-available/nextcloud.conf
* 虚拟主机2（反向代理Collabora Online）：/etc/apache2/sites-available/office.conf
### PHP ###
* php.ini /etc/php/7.0/apache2/php.ini
### Nextcloud ###
* 安装位置 /cloudserver/nextcloud/
* data目录位置 /cloudserver/data

## MySQL ##
请在部署完毕后自行修改MySQL Root账号及nextcloud账号的密码

USER       |PASSWORD<br />
root       |chengyedbroot<br />
nextcloud  |chengyedbnextcloud<br />

数据库：nextcloud

## Nextcloud ##
管理员用户名：ChengYe
管理员密码  ：chengye123

# 须知 #
本镜像为单硬盘镜像，可以部署到任意ECS中。
## HTTPS ##
本镜像已配置HTTPS，所以首次访问可能提示证书错误，请在修改HTTPS配置后尝试访问。
HTTPS配置已包含在虚拟主机的配置文件中，证书目录默认为/etc/apache2/cert/


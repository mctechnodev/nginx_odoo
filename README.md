# NGINX PARA ODOO
## Nginx Odoo 🤖👨🏽‍💻

_Configuracion del archivo default.conf para Reverse Proxy de Odoo_

## Centos 🔧
```
sudo yum install epel-release
sudo yum install nginx
cd /etc/nginx
git clone https://github.com/mamfredym/nginx_odoo
cd nginx_odoo/
sudo cp /etc/nginx/nginx_odoo/default.conf /etc/nginx/default.conf
cd ..
mv default default-temp
mv default.conf default
service ngnix restart
```


## Ubuntu 🚀
```
sudo apt-get install nginx
cd /etc/nginx/sites-available
git clone https://github.com/mamfredym/nginx_odoo
cd nginx_odoo/
sudo cp /etc/nginx/sites-available/nginx_odoo/default.conf /etc/nginx/sites-available/default.conf
cd ..
mv default default-temp
mv default.conf default
service ngnix restart
nginx -s reload
```

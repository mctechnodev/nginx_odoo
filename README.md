# NGINX PARA ODOO
## Nginx como reverse proxy para Odoo 🤖👨🏽‍💻

_Configuracion del archivo default.conf para Reverse Proxy de Odoo_

## Centos 🔧
```
sudo yum install epel-release
sudo yum install nginx
cd /etc/nginx/conf.d/
git clone https://github.com/mamfredym/nginx_odoo
cd nginx_odoo/
sudo cp /etc/nginx/conf.d/nginx_odoo/default.conf /etc/nginx/conf.d/default.conf
cd ..
mv default default-temp
mv default.conf default
sudo service ngnix restart
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
nginx -s reload
```

## Ajustes de IP y Subdominio en Nginx 📖
* _Reemplazar **SUBDOMAIN.DOMAIN.COM** por el dominio un registro con www y otro sin www_
* _Reemplazar **IP_PUBLIC_PRIVATE** por la IP por donde se conectan a Odoo, si es por IP publica o es por IP Privada si cuenta con infraestructura propia_
* _Puede tambien dependiendo la capacidad del servidor, cambiar el timing de 3600 a 720s_
* Luego de cambiar los valores **_REINICIAR NGINX_** ♻️

## Configuracion en Odoo 💾
_Abrir archivo de config de Odoo_
```
nano /etc/odoo/odoo.conf
```
_Cambiar/Adicionar estos parametros en el archivo de configuracion de Odoo_
```
xmlrpc_interface = 127.0.0.1
netrpc_interface = 127.0.0.1
proxy_mode = True
```
_Reiniciar Odoo_
```
sudo service odoo restart
```

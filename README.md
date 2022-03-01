# diyha-dash
Django web server
Install apache2
```
sudo apt install apache2 -y
```
Test on browser useing host ip address. You should get the default Apache page.

## Django stuff for apache
```
sudo apt install libapache2-mod-wsgi-py3
```
Make sure you have the latest python3
```
sudo apt install python3 python3-venv python3-pip
```
configure apache
```
sudo vi /etc/apache2/sites-enabled/000-default.conf
```
enter 
```
Alias /static /home/pi/pidjango/static
<Directory /home/pi/pidjango/static>
   Require all granted
</Directory>

<Directory /home/pi/pidjango/pidjango>
   <Files wsgi.py>
        Require all granted
   </Files>
</Directory>

WSGIDaemonProcess django python-path=/home/pi/pidjango python-home=/home/pi/pidjango/djenv
WSGIProcessGroup django
WSGIScriptAlias / /home/pi/pidjango/pidjango/wsgi.py
```
## git clone the repository
```
git clone
```
create static directory
```
cd diyha-dash
mkdir static
```
install django
```
sudo python3 -m pip install django
```

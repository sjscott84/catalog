Linux Server Setup  
=============
Project for Udacity Full Stack Web Developer Nanodegree

## To access server
  
The server can be found at ip address 52.41.137.76 port 2200  

## Hosted website   

The hosted application can be found at http://52.41.137.76/artists/  

## Software installed to server    

The following software was installed on the server:  

* apache2  
* libapache2-mod-wsgi  
* postgresql  
* git  
* python-pip  
* python-dev  
* build-essential
* Flask  
* sqlalchemy  
* psycopg2  
* oauth2client  
* requests  

## Configuration  

The following configurations were made:

The below was added to /etc/apache2/sites-enabled/000-default.conf:  
  `WSGIScriptAlias / /var/www/myApp/myApp.wsgi  
       <Directory /var/www/myApp/catalog>  
            WSGIProcessGroup catalog  
            WSGIApplicationGroup %{GLOBAL}  
            Order deny,allow  
            Allow from all  
        </Directory>`  
        
The below was added to /var/www/myApp/myApp.wsgi:  
`import sys  
sys.path.insert(0,"/var/www/myApp/")  
from catalog.application import app as application  
application.secret_key = 'super_secret_key'`   


# Linux-Server-Configuration

#### About

This project is submitted under Udacity Full Stack web Development Nanodegree Final Project

#### Server Details

Server Static IP Address 52.66.166.167

Hosted site Url [http:52.66.166.167.xip.io]

#### Grader Password:

ashish

#### Software Requirements:

AWS account with lightsail service activated.

1)Python Pip

2)Postgres

3)httplib2

4)SQLAlchemy

5)Apache2

6)Flask

7)Virtualenv

8)Requests

9)Oauth2client

#### Installation Process for softwares:

    sudo apt-get install apache2		

    sudo apt-get install python-setuptools libapache2-mod-wsgi

    sudo a2enmod wsgi

    cd /var/www

    sudo mkdir FlaskApp

    sudo apt-get install git

    sudo apt-get install python-pip virtualenv

    sudo virtualenv venv

    sudo pip install Flask

    sudo pip install postgresql oauth2client httplib2 requests psycopg2

Grader Key

-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAxOlmcRkqrkZSywi8eV0H+5sXVz/2idP9Uf5oZ3y9m0jCv0K7
BjDe3HI7gwRtW19qPWU+GwcGYDYUAJ/okQ4RpL5eGv6liJIKimer9tJT5r1Bpjit
LioaZ/F8mzbMKguTWsbx6IHoALInDOBamNLI+XNKhyX/03Wmr0IZrJsdpH2rE5pA
N62pkifJs60Fb4LsPM1lEr7iNa/fSKpBrSUJ5qWHiq7YUMNOPb3ATERLYT9n/B3N
Eq3P1ZfL/CIglrUvtQmmq9TAAGvhj4Bdu+mdhbTR8k/j90Upa4mNmAbtBLUoFaMJ
V/IYghfE1Tsj0mVqd5GQh7BUlk5JWN9SLCqb+QIDAQABAoIBAQCdiV27/jZ3VyvF
5CdlsVhBo8L4uuOzQTbZ8n/0y4emRIAKJIkcWtzx4TJbj58uCxgkJmuZk/U15A38
sfKOmoLjGqqPTkuBB9YHBQo/XeZiI+fx5EYpOOYHYtweEakluj0Z0zCWo9fJNr6n
Ppc8zOadK+/kUDJsKyQ/8tI3laIRhlBdmzH6RzV8AYp20O3WL1PulyzsY7oQXuN2
WmQa1GSGVlVhwYEPd4oeuNTcIyzAmDgXslnDdpMAV73K0Dxpj1Xe4zxZ5xHDs0qH
onCCObv9jfyAccbHWWQazJ+hG3IzyHJFCiFMnfJn237TmeiynYsIW5qhzCyptOYb
nAumGxEBAoGBAPRZNXGx1rCOwBRDJVtt8ol4qpNDm2MluKO+eOxD7NEWt+dTL44v
rdYgcYw+vIUJeLhUjOytQmW7cTp/E1WJh4EIZ1fLmFG8vp5MjfwNFnZsdrVma/wY
5peQDT/qnXwi2vhBwCF+XCTpVRjoOAZ5Y7UzZwJz1DhdFeuKNZJZJIX9AoGBAM5N
IBAd+RzG09+pbIidMX+aSZbPmq0iH8Idibb1K2nRwAZHym1vUX8xXDNTVKQHmbl/
hHLD3YQ9GJgJww8z3mSgAx9QjmZmVmbUu+Ra86jSGsCHSiE+ENzBE85GPTVvvqix
I/Lo+qc+srPSBJ3zV37do9xx4iINxxfPHwzrIVCtAoGBAIfsN/aO3sZIIkEjONyr
RIeEQB67NOzqRtOPWOTUxB9ra9GaTJHjo+fBFGjXXTcEFcsz/VCK8Kx2oH3RwoeK
gX4dlp8X+hs9yytzmmfjP+OQYlh2KQuLLnqQ/03WzNQI75W5vY7kI43E3jmEs+Wm
EPjzJxIOLLdN0Ku9rh9CxzZhAoGAKzrEHjx5qAsN+M9C2/m8lpWZGA4WxnLhHscb
xYfoefsm9unyRC5QcIvCW0r58IlbMCDFe1sJvx0iWzGoezYOQx24qcYyoMiPEGtB
mB9q8ZRdYLy4zvB3jhqzcMUNLHZnCGheNReW9pbP0ZiPuR111zLQlHAUx7gFYTrY
sddPmt0CgYBNL+b2nEjHdtaVQgilvKU05APsNyCC6tBHdKDR/MCcJJiljDokp9tb
SQIgJesT5xWi1o8ybBsARbYCOkuQdFPcUirozmw/QJH9BWPLiUJBzku4VA9iMkSL
g1JZQtqTLpIv92K2hqeKeuE7O14rzUyZOmhfA766AZ9SGxc0kaHPKA==

-----END RSA PRIVATE KEY-----


#### How to connect as grader:

save private key provided in your local machine and run the following command

    ssh -i path/to/privatekey -p 2200 grader@52.66.166.167
  
##### Configuring Linux Server:

Updating all packages

    sudo apt-get update
    sudo apt-get upgrade
    
All the packages are updated for your reference a screenshot is attached.

##### Creating grader User:

    sudo adduser grader
    
##### This will add new user

    sudo nano /etc/sudoers
    
##### Below the Root user append the following line

    grader  ALL=(ALL:ALL) ALL
    
This will grant sudo permission to grader

##### Creating a ssh key pair for grader:

On your local machine in terminal/command prompt

    ssh-keygen
    
This will generate public and private ssh keys which is saved to .ssh folder

Then in your virtual machine change to newly created user

    sudo su - grader
    
Create a new directory .ssh and new file authorized_keys in that directory

    mkdir .ssh
    sudo nano .ssh/authorized_keys
    
Copy the public key with .pub extension to authorized_keys and save the file

    chmod 700 .ssh
    chmod 644 .ssh/authorized_keys
    
700 will give read write and execute permission to user.
644 prevent other user from writting in to file. Then restart ssh server

    sudo service ssh restart
    
Now from your log in to grader with private key generated

Use this for connecting from local terminal

    ssh -i .ssh/id_rsa grader@ipaddress 
OR
Use this for connecting from local terminal

    ssh grader@ip_address 
    
Changing the ssh port to 2200

    sudo nano /etc/ssh/sshd_config
    
Change port 22 to port 2200

Restart the ssh server

    service ssh restart
    
##### Note: Before Logging using ssh add custom TCP port 2200 under lightsaail firewall in networking tab in lightsail instance console

Now Login using command like this

    ssh -i .ssh/id_rsa -p 2200 grader@ipaddress
    
Disabling ssh login as root

    sudo nano /etc/ssh/sshd_config

make change PermitRootLogin no

Configurating Uncomplicated Fire Wall

    sudo ufw allow 2200/tcp
    sudo ufw allow 80/tcp
    sudo ufw allow 123/udp
    sudo ufw enable
    
This will allow all required ports and enables the ufw

After that

    sudo ufw status
It will display all allowed ports

Changing time Zone

    sudo dpkg-reconfigure tzdata

select none from list and then select utc.

Installing Apache2
In terminal

    sudo apt-get install apache2

Now mod_wsgi

    sudo apt-get install python-setuptools libapache2-mod-wsgi

Enable mod_wsgi

    sudo a2enmod wsgi

Setting up your flask application to work with apache2

Creating a flask app

In /var/www directory create a new folder sudo mkdir FlaskApp

    Install git

    sudo apt-get install git

move to the FlaskApp cd FlaskApp

In that direcory clone your github repository

    sudo git clone https://github.com/username/repo_name.git

Rename your repository to FlaskApp

Then rename your project file to __init__.py

Error : While accesssing the client_secrets.json file

PROJECT_ROOT = os.path.realpath(os.path.dirname(__file__))
json_url = os.path.join(PROJECT_ROOT, 'client_secrets.json')
CLIENT_ID = json.load(open(json_url))['web']['client_id']

Place json_url instead client_secrets.json in script

Install and configuring postgresql for project

Install Postgres sudo apt-get install postgresql

login to postgres sudo su - postgres

postgres shell psql

create user CREATE USER catalog WITH PASSWORD 'password';

permit user to createdb ALTER USER catalog CREATEDB;

Create a db name catalog with user catalog CREATE DATABASE catalog WITH OWNER catalog;

connect to db \c catalog

revoke all permission to public REVOKE ALL ON SCHEMA public FROM public;

Give schema permission to user catalog GRANT ALL ON SCHEMA public TO catalog;

exit from db \q exit from postgres exit

Change the database connection in both db_setup.py and init.py as engine = create_engine('postgresql://catalog:password@localhost/catalog')

Create a Virtuval Flask env for our app to be isolated from server environment for better stability(Extra Credit/Optional)

In this step, we will create a virtual environment for our flask application.

We will use pip to install virtualenv and Flask. If pip is not installed, install it on Ubuntu through apt-get.

    sudo apt-get install python-pip  

If virtualenv is not installed, use pip to install it using following command:

    sudo pip install virtualenv

Give the following command (where venv is the name you would like to give your temporary environment):

    sudo virtualenv venv
    
Now, install Flask in that environment by activating the virtual environment with the following command:

    source venv/bin/activate 
    
Give this command to install Flask inside:

    sudo pip install Flask 
    
Next, run the following command to test if the installation is successful and the app is running:

    sudo python __init__.py 
    
It should display “Running on http://localhost:5000/” or "Running on http://127.0.0.1:5000/". If you see this message, you have successfully configured the app.

To deactivate the environment, give the following command:

     deactivate

Now you are ready with your applicatiom

Configure and Enable a New Virtual Host

     sudo nano /etc/apache2/sites-available/FlaskApp.conf

In this add the following code

<VirtualHost *:80>
 	ServerName mywebsite.com
 	ServerAdmin admin@mywebsite.com
 	WSGIScriptAlias / /var/www/FlaskApp/flaskapp.wsgi
 	<Directory /var/www/FlaskApp/FlaskApp/>
 		Order allow,deny
 		Allow from all
 	</Directory>
 	Alias /static /var/www/FlaskApp/FlaskApp/static
 	<Directory /var/www/FlaskApp/FlaskApp/static/>
 		Order allow,deny
 		Allow from all
 	</Directory>
 	ErrorLog ${APACHE_LOG_DIR}/error.log
 	LogLevel warn
 	CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

Enable the virtual host sudo a2ensite FlaskApp

Disabling the default apache2 page sudo a2dissite 000-default.conf

Create the .wsgi File
```
cd /var/www/FlaskApp
sudo nano flaskapp.wsgi 
```
Add the following code

#!/usr/bin/python
 import sys
 import logging
 logging.basicConfig(stream=sys.stderr)
 sys.path.insert(0,"/var/www/FlaskApp/")

 from FlaskApp import app as application
 application.secret_key = 'Add your secret key'
save and exit

 Deploying flask app with apache2 is referred from [Digital ocean](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps)

Installing require modules

You can either install all modules on your machine or create a virtual environment for the project and install the modules To Create virtual environment: sudo virtualenv venv To activate virtual environment: source venv/bin/activate pip install flask sqlalchemy psycopg2 requests oauth2client

To deactivate virtual environment: deactivate

Setting up your Google Oauth2
Login to your developer console and select your project and edit OAuth details as following

Javascript origin http://static_ip_address.xip.io

redirect URI

http://static_ip_address.xip.io\callback

http://static_ip_address.xip.io\gconnect

http://static_ip_address.xip.io\login

xip.io is a free DNS which will be the same as using IP address

#### Final Step:

Restart your apache2 server

    sudo service apache2 restart

"# Linux-"
## References

https://www.digitalocean.com
https://github.com/crazyvny


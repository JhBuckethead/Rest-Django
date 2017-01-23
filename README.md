# Rest-Django
Proyecto que implementa servicio REST con el uso del framework de Django (Linux)

models.py
---------
from django.db import models
from pygments.lexers import get_all_lexers
from pygments.styles import get_all_styles
    
LEXERS = [item for item in get_all_lexers() if item[1]]
LANGUAGE_CHOICES = sorted([(item[1][0], item[0]) for item in LEXERS])
STYLE_CHOICES = sorted((item, item) for item in get_all_styles())
    
    
class Materia(models.Model):
    created = models.DateTimeField(auto_now_add=True)
    title = models.CharField(max_length=100, blank=True, default='')
    code = models.CharField(max_length=200, blank=True)
    linenos = models.BooleanField(default=False)
    language = models.CharField(choices=LANGUAGE_CHOICES, default='python', max_length=100)
    style = models.CharField(choices=STYLE_CHOICES, default='friendly', max_length=100)
    
    class Meta:
        ordering = ('created',)
----------------
admin.py

from django.contrib import admin

# Register your models here.

from escuela.models  import *


admin.site.register(Materia)
--------------------------------------
CORS_ORIGIN_WHITELIST = (
    'google.com',
    'hostname.example.com',
    'localhost',
    '127.0.0.1:9000'
)
---------------------------

INSTALLED_APPS = (
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'corsheaders',
    'rest_framework',
    'escuela',
)
---------------------------

Requeriments

backports.shutil-get-terminal-size==1.0.0
decorator==4.0.11
Django==1.8
django-cors-headers==2.0.0
djangorestframework==3.5.3
enum34==1.1.6
httpie==0.9.9
ipython==5.1.0
ipython-genutils==0.1.0
pathlib2==2.2.0
pexpect==4.2.1
pickleshare==0.7.4
prompt-toolkit==1.0.9
ptyprocess==0.5.1
Pygments==2.1.3
requests==2.12.4
scandir==1.4
simplegeneric==0.8.1
six==1.10.0
traitlets==4.3.1
wcwidth==0.1.7

)
---------------------------

apt-get install python-setuptools
apt-get install python-dev

LIBRERIAS DE PYTHON

easy_install pib
pip install virtualenv

CREAR ENTORNO VIRTUAL

virtualenv rest
source/rest/bin/activate

REQUERIMIENTOS PAR INSTALAR EL ENTORNO

pip install -r requerimientos.txt

CREAR UN PROYECTO DE DJANGO

#ubicarse en home

cd proyectos-arquitectura-computadoras
django-admin startproject institucion

#se debe tener institucion y manage.py
# para instalar el rest django se debe tener en installed_app

cd institucion

#me aseguro que estoy en el directorio donde esta el manage.py

python manage.py startapp escuela

#Se modifica el archivo settings.py, admin.py y el models.py

python manage.py makemigrations escuela
pythno manage.py miagrate

python manage.py createsuperuser

#se llenan los datos necesarios

jhonson
epifon94

python manage.py runserver

#debe salir el servicio de rest poniendo

http://localhost:8000/snippets/

#Se cambia el nombre en modes.py def self

#instalar apache

apt-get install apache2

#revisamos que este instalado

service apache2 status
service apache2 start
service apache2 restart
service apache2 stop

#crear una carpeta en el home

mkdir public_html

sudo a2enmod userdir
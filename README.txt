README.txt 

THIS IS A LOCAL GIT REPOSITORY FOR DJANGO COURSE BY LONDON DEVELOPER

S3
Git Markdown
https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
python.gitignore
https://gist.github.com/LondonAppDev/66c3291e4f487ac92fcc96735e44c35e

S4
vagrant init
replace content in Vagrantfile using link -
https://gist.github.com/LondonAppDev/d990ab5354673582c35df1ee277d6c24

useful for django projects used by londondevelopers

vagrant up

vagrant ssh

S5
L11
vagrant ssh
mkvirtualenv profiles_api --python=python3
 
deactivate

L12
workon profiles_api

pip install django==1.11
pip install djangorestframework==3.6.2

L13
mkdir src
cd /vagrant/src 

django-admin.py startproject profiles_project

cd profiles_project

python manage.py startapp profiles_api

L14
profiles_project/profiles_project/settings.py
INSTALLED_APPS 
	'rest_framework',
	'rest_framework.authtoken',
	'profiles_api',

L15
workon profiles_api

cd /vagrant

pip freeze 
pip freeze > requirements.txt 

L16
vagrant up 
vagrant ssh 
workon profiles_api

cd /vagrant/src/profiles_project

python manage.py runserver 0.0.0.0:8080

git status
git add .
git commit -am ""

S6
L17
https://docs.djangoproject.com/en/1.11/topics/db/models/

L18
https://gist.github.com/LondonAppDev/01feb984211e1237f81ca3e4bdb1eeb7
https://docs.djangoproject.com/en/1.11/ref/models/fields/
https://docs.djangoproject.com/en/1.11/topics/auth/customizing/#auth-custom-user

User Profile Model -
profiles_api -
models.py  -

L19
https://gist.github.com/LondonAppDev/9e6ba4ea580e5ee4bc3c04d3914c8119
https://docs.djangoproject.com/en/1.11/topics/auth/customizing/#django.contrib.auth.models.BaseUserManager.normalize_email

User Profile Manager -
profiles_api -
models.py  -

L20
settings.py -
AUTH_USER_MODEL = 'profiles_api.UserProfile'

L21
Database Migration 

python manage.py makemigrations
python manage.py migrate


S7
L22
Adding django admin.
https://docs.djangoproject.com/en/1.11/ref/contrib/admin/

create superuser 
python manage.py createsuperuser
Email: prats@dprats.xyz
Name: prats ran
Password: superuser

L23
Enable Django Admin

profiles_api -
admin.py -

L24
Test Django Admin 

python manage.py runserver 0.0.0.0:8080

localhost:8080/admin 
Email: prats@dprats.xyz
Password: superuser

S8
L25
APIViews
http://www.django-rest-framework.org/api-guide/views/

L26
https://gist.github.com/LondonAppDev/c422fb5ca84cfc626bd1a5307710840e
Create an APIView 

L27
Configure View URL
https://docs.djangoproject.com/en/1.11/topics/http/urls/
https://gist.github.com/LondonAppDev/0009a1f158eb6433ba42ac605346d1fa

profiles_project -
urls.py -

profiles_api -
urls.py

L28
Testing API view 








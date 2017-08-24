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

L29
http://www.django-rest-framework.org/api-guide/serializers/
http://www.django-rest-framework.org/api-guide/fields/
https://gist.github.com/LondonAppDev/71931a9a8306e3aa8face1faa6735273

Create a Serializer
profiles_api -
serializers.py 

L30
http://www.django-rest-framework.org/api-guide/status-codes/
https://gist.github.com/LondonAppDev/1cf65a9b5029510a1b94a12f6edfa5fd

Add POST method to APIView 
profiles_api -
views.py -

L31
Test POST method in API View 
python manage.py runserver 0.0.0.0:8080

localhost:8080/api/hello-view/

L32
Add PUT, PATCH, DELETE methods
profiles_api -
views.py -

L33
TEST PUT, PATCH, DELETE methods 


S9
L34
VIEWSet
-Model Operations for api functions

L35
Create a Simple ViewSet
https://gist.github.com/LondonAppDev/778a13391b25098ed249ccc970e93eed

profiles_api -
views.py -

L36
Add a URL Router
https://gist.github.com/LondonAppDev/fcb55671f7fa298d691166106c03164b

profiles_api -
urls.py -

L37
Test Viewset
localhost:8080/api/

L38
Add CREATE, RETRIEVE, UPDATE, PARTIAL_UPDATE AND DESTROY functions to view sets
https://gist.github.com/LondonAppDev/71cd7309d67ec4ae0706ed287643f532

profiles_api -
views.py -
HelloViewSet

L39
Test ViewSet

localhost:8080/api/
localhost:8080/api/hello-viewset/


S10
L40
Profiles API 

L41
Create user Profile Serializer
http://www.django-rest-framework.org/api-guide/serializers/#modelserializer
https://gist.github.com/LondonAppDev/526d70391ba64329ed1782f89875bf84

profiles_api -
serializers.py -
UserProfileSerializer

L42
Create Profiles VIewset
https://gist.github.com/LondonAppDev/294e9a01f9774435352aafd3697ab541

profiles_api -
views.py -
UserProfileViewSet

L43
Register profile viewset with URL router
https://gist.github.com/LondonAppDev/79d73f8dee46b1392f0a11236e202725

profiles_api -
urls.py -

L44
Test Creating a profile 

L45
Create Permission class
http://www.django-rest-framework.org/api-guide/permissions/
https://gist.github.com/LondonAppDev/e053bce06a9b3a06dcdc4d158f5b0417

profiles_api -
permissions.py -
UpdateUserOwnProfile

L46
Add Authentication and permissions to viewset 
https://gist.github.com/LondonAppDev/0af322f8fa7b0c47df8dcbe351a35808

profiles_api -
views.py -
UserProfileViewSet

L47
Add Search Profile Features

profiles_api -
views.py -
UserProfileViewSet

L48
Test Searching Profiles 

S11
L50
Create a Login API ViewSet 
https://gist.github.com/LondonAppDev/21a592854fbed9a46309aa1450d8308a
https://gist.github.com/LondonAppDev/321f22d6969426f9eb7153196881accb

profiles_api -
views.py -
urls.py -

L51
Test Login API 

localhost:8080/api/
localhost:8080/api/login/

L52
Set Token Header Using ModHeader extension in chrome browser


S12
L53
Plan Profile Feed API 


L54
Add New Model Item
https://gist.github.com/LondonAppDev/e32cb01d46198808edfd62b047a1e17c

profiles_api -
models.py -
ProfileFeedItem

L55
Create and RUn Model Migration

python manage.py makemigrations 
python manage.py migrate

L56
Add Profile Feed Model to Admin 
https://gist.github.com/LondonAppDev/225e46e2eaaf6c8e3aef9006540bf8c5

profiles_api -
admin.py -

L57
Create Profile Feed Item Serializer 
https://gist.github.com/LondonAppDev/555a9a833253a3d41ec5c0eb829a0291

profiles_api -
serializers.py -
ProfileFeedItemSerializer

L58
Create ViewSet for our Profile Feed Item
https://gist.github.com/LondonAppDev/832577ec1f2db1b467de62ae56d7e87c
https://gist.github.com/LondonAppDev/95deb8de5a98b9a1def60a1b0cdba46c

profiles_api -
views.py -
UserProfileFeedViewSet

urls.py -

L59
Test Feed API 

L60
Add Permissions for Feed API
https://gist.github.com/LondonAppDev/d21e13c5bf62a380ac73989d4dc4da9f
https://gist.github.com/LondonAppDev/a7e8a47d46263cd0f8b7af95dcfb0b6f

profiles_api -
permissions.py -
PostOwnStatus

views.py -
UserProfileFeedViewSet

L61
Test Feed API Permissions

127.0.0.1:8080/api/profile/
127.0.0.1:8080/api/login/

127.0.0.1:8080/api/feed/
127.0.0.1:8080/api/feed/1/

L62
Restrict viewing status updates to logged in users

profiles_api -
views.py -
UserProfileFeedViewSet

L63
Test New Private Feed 

Uncheck Header in ModHeader
127.0.0.1:8080/api/feed/ 

S13
L64
Introduction to deploy our app to AWS
https://aws.amazon.com/free/
https://github.com/

L65
https://github.com/

setup github account/password or ssh key pairs
setup new githib repository
on local add remote repo 
on local push to remote 

L66
Add Deploy scripts and configs to our project 
https://uwsgi-docs.readthedocs.io/en/latest/
https://gist.github.com/LondonAppDev/7090d8097553ab82209adb1809304d0e
https://gist.github.com/LondonAppDev/4a3dd0dfc7aaa90821309a031abb5022
https://gist.github.com/LondonAppDev/74e8a37ff1ac8f1afe758ea563c54048

git project -
add deploy dir 

edit requirements.txt 

deploy\nginx_profiles_api.conf
deploy\supervisor_profiles_api.conf
deploy\server_setup.sh

change to Unix(LF) EOL endings























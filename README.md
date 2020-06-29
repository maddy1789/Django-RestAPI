# Django-RestAPI

This is my learning experience toward Django and RestAPI.
I will note down all the process I will make step-by-step to create a simple Django RestAPI.

I will be creating this project in Virtual Environment.

1. Create a virtual environment, I will be using command prompt and go to the project folder and type,
   => python -m venv venv
   This will create virtual environment for our project and folder named venv will be created.

2. To start virtual environment, type
   => go to folder venv\Scripts and tpye activate, or else
   =>venv\Scripts\activate
   This activate the virtual environment

3. Now we are ready to install all our requirement libraries,
   1. Django            =>  pip install django
   2. Django RestAPI    =>  pip install djangorestframework
   3. Django CorsHeader =>  pip install django-cors-headers

# Check all the libraries installed, type => pip freeze
# asgiref==3.2.10
# Django==3.0.7
# django-cors-headers==3.4.0
# djangorestframework==3.11.0
# pytz==2020.1
# sqlparse==0.3.1

4. Create a Django project
   => django-admin.py startproject <projectname> .
   for e.g. django-admin.py startproject proj_Countries .
   # Add . at the end to avoid multiple folder to created

5. Create a Django App
   => python manage.py startapp <appName>
   for e.g. python manage.py startapp app_countries

6. Registering Application, We need to register all the apps and libraries to Django Project

   We have installed #djangorestframework, #django-cors-headers and create a app #app_countries. We will be registering this libraries and app in our Django project. To register we need to go to our Django Project i.e. proj_Countries and open settings.py
   => setting.py, go to INSTALLED_APPS section and add,
      # 'rest_framework',
      # 'corsheaders',
      # 'app_countries.app.AppCountriesConfig'

   We will also need to register the Middleware for corsheader,
   => setting.py, got to MIDDLEWARE section and at the top add,
      # 'corsheaders.middleware.CorsMiddleware'

7. To database connection in Django project, we will be using MySQL DB. To connect to MySQL we will be using
   # mysqlclient
   But for windows its difficult to install mysqlclient, so we need to download from below link,
   # https://www.lfd.uci.edu/~gohlke/pythonlibs/#mysqlclient
   I have already downloaded mysqlclient-1.4.6-cp38-cp38-win32.whl.
   After download, => pip install <downloaded file>
   => pip install mysqlclient-1.4.6-cp38-cp38-win32.whl

8. In setting.py, in DATABASES section add mysql connection information,
   'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'countriesdb',
        'USER': 'django_admin',
        'PASSWORD': 'He110@MySQL',
        'HOST': '127.0.0.1',
        'PORT': '3306'
    }




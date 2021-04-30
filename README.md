# Installation and Process Instructions

### Creates a virtual environment for the project

`pip3 install virtualenv`
`mkdir environments`
`virtualenv django_prototype`

### Activare environment

`source django_prototype/bin/activate`

### Install Django

`pip3 install django`

### Make app project

`django-admin startproject django_team6_prototype`

### Create a server to view the prject in the browser

`python manage.py runserver`

### Creating the actual app

`python manage.py startapp project`

### Creates migrations

`python manage.py makemigrations`

## MySQL set-up process

### Installing mysql using brew

`brew install mysql`

I then installed MySQL Workbench (version 8.0.19)

I created a new schema called team_6 with a user cpintor and password team6 and assigned the user all Administrative Roles and Schema Privilages

### Start up MySQL service

 `brew services start mysql

### Installing mysql client within your env directory

`pip install mysqlclient`

Chane the Db settings in settings.py from

```sql
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}
```

to

```sql
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'team_6',
        'USER': 'cpintor',
        'PASSWORD': 'team6',
        'HOST': '127.0.0.1',
        'PORT': '3306',
    }
}
```

### Run a migration, refresh the databse in MySQL WorkBench

`python manage.py migrate`

### Creates admin user for web app admin page user: cpintor, pw: team6project

`python manage.py createsuperuser`

### After creating the post models

`python manage.py makemigrations`

### To make changes into database

`python manage,py migrate`

## Part 8

### For images

`pip install pillow` for images

### Run after installing Pillow

`python manage.py makemigrations`

### To apply changes to DB

`python manage.py migrate`

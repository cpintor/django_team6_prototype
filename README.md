`pip3 install virtualenv` # creates a virtual environment for the project 
`mkdir environments`
`virtualenv django_prototype`
`source django_prototype/bin/activate` # activare environment
`pip3 install django` # install django
`django-admin startproject django_team6_prototype` # make app project
`python manage.py runserver` # create a server to view the prject in the browser
`python manage.py startapp project` # creating the actual app
`python manage.py makemigrations` # creates migrations
`brew install mysql` # installing mysql using brew

I then installed MySQL Workbench (version 8.0.19)

I created a new schema called team_6 with a user cpintor and password team6 and assigned the user all Administrative Roles and Schema Privilages

`brew services start mysql # start up MySQL service
`pip install mysqlclient` # installing mysql client within your env directory

Chane the Db settings in settings.py from

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}

to 

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

`python manage.py migrate` # run a migration, refresh the databse in MySQL WorkBench

`python manage.py createsuperuser` # creates admin user for web app admin page user: cpintor, pw: team6project

`python manage.py makemigrations` # after creating the post models

`python manage,py migrate` # to make changes into database

#### part 8 
`pip install pillow` for images
`python manage.py makemigrations` # run after installing Pillow
`python manage.py migrate` # to apply changes to our DB
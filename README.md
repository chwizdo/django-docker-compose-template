# Django Docker Compose Template

A starter template to create a new Django project that runs in a Docker environment.

✅ Python 3

✅ Docker Compose

✅ PostgreSQL

## How to setup?

1. Create a new Django project by executing this command at the root of the project directory.

```
sudo docker-compose run web django-admin startproject chwizdo_project .
```
2. In your project directory, edit the chwizdo_project/settings.py file.
```
# settings.py
   
import os
   
[...]
   
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': os.environ.get('POSTGRES_NAME'),
        'USER': os.environ.get('POSTGRES_USER'),
        'PASSWORD': os.environ.get('POSTGRES_PASSWORD'),
        'HOST': 'db',
        'PORT': 5432,
    }
}
```
3. Finally, run the docker container by executing this command.
```
docker-compose up
```

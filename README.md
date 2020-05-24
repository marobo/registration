# Django Registration Template

Registration templates

## Background

This packages based on the following [macdhuibh](https://github.com/macdhuibh/django-registration-templates) and [bitbucket](https://bitbucket.org/devdoodles/registration_templates/src) repo:

```
https://github.com/macdhuibh/django-registration-templates
https://bitbucket.org/devdoodles/registration_templates/src
```

I was modified this to include some style for all registrations templates page


## Usage

First clone the repo:

```
git clone https://github.com/marobo/registration.git
```

You can try run this registration project on your machine:

```
pip install -r requirements.txt
./manage.py migrate
./manage.py createsuperuser
./manage.py runserver
```

and then visit the site

```
http://127.0.0.1:8000
```

If you like to use on your project please move the registration directory to your templates directory

Please follow the step bellow:

```
cd templates
mv registration path/to/your/templates/registration
```

`base.html` and `index.html` inside `templates/` are also included but most likely, you'll already have those present in your templates directory.

Move static file to your static directory:

```
cd ..
cd static
mv css path/to/your/static/css
mv js path/to/your/static/js
```

Adding those line bellow to your `project/urls.py` :

```
from django.conf.urls import include

urlpatterns = [
    path('accounts/', include('django.contrib.auth.urls')),
]
```

Change this  `'DIRS': []`, on your `settings.py` to `'DIRS': [os.path.join(BASE_DIR, 'templates')],`
See in bellow:

```
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]
```

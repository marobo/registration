# Django Registration Template

Registration templates

## Background

This package based on the following [macdhuibh](https://github.com/macdhuibh/django-registration-templates) and [bitbucket](https://bitbucket.org/devdoodles/registration_templates/src) repos:

```
https://github.com/macdhuibh/django-registration-templates
https://bitbucket.org/devdoodles/registration_templates/src
```

I modified this to include some style in each page


## Usage

If you wan to test on your machine, the first thing you need to clone this repo into your local machine:

```
git clone https://github.com/marobo/registration.git
```

Install requirements / Django

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

If you like to use on your project please move the `registration` directory to your templates directory by follow the step bellow:

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

Adding those line below to your `project/urls.py` :

```
from django.conf.urls import include

urlpatterns = [
    path('accounts/', include('django.contrib.auth.urls')),
]
```

Change this  `'DIRS': []`, on `settings.py` to `'DIRS': [os.path.join(BASE_DIR, 'templates')],`

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

# Testing

Run the server and then visit login page, you will see a nice login form

```
http://127.0.0.1:8004/en/accounts/login/
```

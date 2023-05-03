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

To use this on Django Project, you need to clone this repo into your Django project directory
```
git clone https://github.com/marobo/registration.git
rm -rf registration/.git/
rm registration/.gitigonre
```

Move registration folder to the your existing templates folder
```
mv registration/registration templates/
```

Move static folder to your existing static folder, this icluding, `animate.css`, `bootstrap.min.css` and `registration.css` files
```
mv static/css static/css
```

Adding those lines below to your URLconfig in `project/urls.py` file :

```
from django.conf.urls import include

urlpatterns = [
    path('accounts/', include('django.contrib.auth.urls')),
]
```

Change this  `'DIRS': []`, on `settings.py` to `'DIRS': [os.path.join(BASE_DIR, 'templates')],`
Django will automatically look for the app name and the folder inside naming 'templates'


```
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [os.path.join(BASE_DIR, 'templates')],
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
http://127.0.0.1:8000/accounts/login/
```

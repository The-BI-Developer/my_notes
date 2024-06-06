A new project deserves its own venv

#Creating framework
django-admin start-project <project_name>

#django framework
. <my_app's directory is here>
├── db.sqlite3 #python manage.py migrate .
├── <project_name> #django-admin start_project <project_name> .
│   ├── asgi.py
│   ├── __init__.py
│   ├── __pycache__
│   │   ├── __init__.cpython-311.pyc
│   │   ├── settings.cpython-311.pyc
│   │   ├── urls.cpython-311.pyc
│   │   └── wsgi.cpython-311.pyc
│   ├── settings.py #INSTALLED_APPS = ["django.contrib.admin", ...., "pages.apps.PagesConfig"]
│   ├── urls.py
│   └── wsgi.py
├── manage.py #use with runserver/migrate
└── pages #created separately later
    ├── admin.py
    ├── apps.py
    ├── __init__.py
    ├── migrations
    │   ├── __init__.py
    │   └── __pycache__
    │       └── __init__.cpython-311.pyc
    ├── models.py #2 - the fourth missing is an html template
    ├── __pycache__
    │   ├── admin.cpython-311.pyc
    │   ├── apps.cpython-311.pyc
    │   ├── __init__.cpython-311.pyc
    │   ├── models.cpython-311.pyc
    │   ├── urls.cpython-311.pyc
    │   └── views.cpython-311.pyc
    ├── tests.py
    ├── urls.py #3
    └── views.py #4

// urls.py + views.py + models.py + html template = single webpage linked to database

#Every web framework needs a way to generate html files; this is done via TEMPLATES in django



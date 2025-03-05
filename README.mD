### To create a django project
django-admin startproject <nameofapplication>

### How to run a django project
python manage.py runserver

### DJANGO PROJECT FILES
1. mange.py :: command line utility allowing us to access the django project : entry file
2. todolist/ : this directory is the actual python project
3. __init__.py : this is anb empty file that indicates above directory is a python project
4. asgi.py : an entry file for ASGI compatible web servers to serve your project
5. wsgi.py : an entry file for WSGI compatible web servers to serve your project
6. setting.py : settings/configuration file for the django project
7. urls.py : these are url declarations that map to our django app

### HOW TO CREATE AN APP INSIDE A DJANGO PROJECT
python manage.py startapp <nameoftheapp>
### register the app
- go to settings.py and include the app using the appname 

### DJANGO APP FILES
1. migrations/ : database migration files (empty initially)
2. __init__.py : indicates the app is a python application
3. admin.py : used to register models for the django admin panel
4. apps.py : contains the app configurations
5. models.py : defines the database models (tables)
6. tests.py : contains test cases for the app
7. views.py : handles request-response logic (functional/controller)
8. urls.py : (manually created in the application level);  defines url patterns for the app

### JINJA TEMPLATING
this is a syntax used to create django interfaces
- to create templates 
a. inside the app folder create a templates folder
b. inside the templates create .html files, .css , .js
c. to consolidate the templating for our project, modify the following
   - set a global template directory for referencing our templates i.e.
    move the todolist template folder to the global perspective i.e. 
    root directory level
   - register this change in settings.py for the project under the templates
     directory settings

      'DIRS': [BASE_DIR / 'templates'], # add this line
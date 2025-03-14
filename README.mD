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
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


### DATABASES    
organised collection of data that allows user to store, retrieve, update and delete information 
more efficiently
### TYPES OF DATABASES
1. relational databases
- stores data in tables: rows(records) and columns(fields)
- tables can be related
  - uses the SQL query language
2. NoSQL Databases
3. in-memory databases

### WHY USE DB's
1. persistent data storage
2. efficient retrieval
3. data relationship
4. security and integrity

### USING DB's IN DJANGO
1. define our model data
2. use django migration commands to convert our model into an actual database table
3. object relational mappers(ORM'S) to interact with the db using python code instead of 
   raw SQL statements

### TO CONVERT MODELS TO TABLES
1. python manage.py makemigrations appname
2. python manage.py migrate

### STEPS TO INCLUDE DB PERSISTENCY FOF PROJECTS
models.py : converted t db tables by django
after defining models manage.py
1/ python manage.py makemigrations appname
2/ python manage.py migrate

### STEPS TO ADD A DATA SOURCE
1. doubleclick on the db.sqlite3 file
2. or simply from pycharm select the database icon
3. click the + sign or the prompt to create the data source
   (for development use sqlite3)

   
### RELATION  DATABASES : DATABASE RELATIONSHIPS
1. one-to-many relationships
  -taskers table (contain the users who will perform the tasks)
  -task table (contains the tasks)
to establish a one-to-many relationship establish a ForeignKey- a unique key 
pointing to a unique reference in another db table

### HOW TO ADD IMAGES (STATIC)
1. Django uses static directory
PROJECT ROOT DIRECTORY => static/ => images/
2. add {% load static %} at the top of the html file
3. add this to the settings.py 
STATICFILES_DIRS = [
   os.path.join(BASE_DIR/ 'static'),
]
4. remember to import os


###  DJANGO ADMIN
create a super user for content management
1. register your models in admin.py
2. creating a super admin user for the project
   python manage.py createsuperuser
3. visit the link appurl/admin - use the super credentials to log in

### DJANGO APIs(application programming interface)
is a set of rules that allows different software applications to communicate with each other



Frontend(HTML <CSS(web) , Android(Jetpack compose) , React Native, Reactjs => Backend 
(server scripting(python->django), database)


### think of an API as a waiter in a restaurant
1. you(frontend/client) make an order(request)
2. the waiter(API) takes the request to the kitchen(server/backend)
3. the kitchen(server) prepares the food(process the request)
4. the waiter(API) brings back the meal(response) to you

### TYPES OF APIs
1. REST API => uses HTTP methods::
- GET :: use this to request data from servers (default)
- POST:: use this to save or send data to servers
- PUT :: use this to update data on servers
- PATCH:: use this to update only a section of data
- DELETE:: use this to remove data from our servers
2. GraphQL API => Allows clients/frontends to access data only when needed
3. SOAP => uses XML methods / older (secure)
4. WebSocket API => enable real time data transfer (chat applications)

### STEPS TO CREATE AN API PROJECT IN DJANGO
1. install djangorestframework :: pip install djangorestframework
2. add djangorestframework as part of the installed apps
3. have views return data as .json files

### JSON (JavaScript Object Notation)
This is an interchangeable data format that can be used across any application

python manage,py startapp todolistappapi
pip install djangorestframework
pipx install djangorestframework
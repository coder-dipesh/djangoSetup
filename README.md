## Complete Project Setup Guide in Django :fire::rocket:
<hr>

Before you start below steps, make sure you have [python](https://www.python.org/downloads/) installed on your system.

Check if python is available on your system or not through below command. 

```
$ python -V
```

If it is available on your system you are good to go :rocket:
Make your project directory via below commands.

```
$ mkdir MyProject
$ cd MyProject
```

Here, What it does is It creates a new directory named "MyProject" and then jump inside it.

### Creating a Python environment
 After creating a directory we need to install and setup the virtual environment around it.
 For installing virtaulenv type the command.

```
$ pip install virtualenv
```

After installing virtualenv, we need to setup a virtual environment named env in our current Project directory.
To do so type command.

```
$ virtualenv env
```
And then we need to activate the virtual environment.

```
$ env\Scripts\activate    
```

### Installing Django 

Now you can see a virtual environment name (env) in the beginning of the command prompt. Then we’ll install the Django in the current directory.

```
(env)$ pip install django
```

After installing Django if you want to check the installation has succeeded.Execute command.
```
(env)$  django-admin --version
```
### Creating your first project

After installing Django into your system, we are good to make our first Django web application project. For making the application type the command.


```
(env)$  django-admin startproject mySite
```
After ```django-admin startproject``` you can choose whatever you want to keep the name of your application. For this demo we have choosed mySite.

When application is successfully created you may see the following project structure.
Here, MyProject is the root directory containing all the project resources, files and sub-directories.

```
MyProject/
       env/
       manage.py
       mySite/
            __init__.py
            settings.py
            urls.py
            asgi.py
            wsgi.py

```

Now to make sure if your project has correctly setuped or not. Jump inside you project and run the following command.

```
(env)$ cd mySite
```
### Running the development server

Now to run django project we need to run the following command

```
(env)$ python manage.py runserver
```
After executing the command you may see 

```
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).

You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
March 04, 2022 - 23:33:30
Django version 4.0.3, using settings 'mySite.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CTRL-BREAK.
```
Now we can visit our website at http://127.0.0.1:8000/ 
Congratulations!! You have successfully setup your first django web application.
<hr>

### Creating an application

This is not the end of it. You can add different apps in your project according to your requirements. To add apps in your project you need to run command.

```
(env)$ python manage.py startapp accounts
```
You can change app name as per your requirements.

After executing the command your project structure should look something like

```
MyProject/
     env/ 
     manage.py
     mySite/
           __init__.py
           settings.py
           urls.py
           asgi.py
           wsgi.py
     accounts/
           __init__.py
           admin.py
           apps.py
           models.py
           tests.py
           views.py
```

Here we can see ```accounts/``` app is added with python sub files, each files are responsible for different operation.


Everytime we create new app we need to mention in ```settings.py``` file of main project(In this demo, ```mySite > settings.py```) in ```INSTALLED_APPS``` field

```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    'accounts', # Newly created app
]
```

Now you can add more apps in your project according to you requirements of the applications. And create a new django web application from scratch.


### Creating the Polls app

Django comes with a utility that automatically generates the basic directory structure of an app, so you can focus on writing code rather than creating directories.  

To create your app, make sure you’re in the same directory as manage.py and type the following command:

```
py manage.py startapp polls
```

That’ll create a directory polls, which is laid out like this:

```
polls/
    __init__.py
    admin.py
    apps.py
    migrations/
        __init__.py
    models.py
    tests.py
    views.py
```

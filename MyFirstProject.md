### Creating a project

In the command line, cd into a directory where you’d like to store your code, then run the following command:

```
django-admin startproject mysite
```

This will create a mysite directory in your current directory

[Problems running django-admin](https://docs.djangoproject.com/en/4.0/faq/troubleshooting/#troubleshooting-django-admin)

### The Devlopment Server

Let’s verify your Django project works.

In the mysite directory run the following commands:

```
 py manage.py runserver
```
&nbsp; 

If you have unapplied migrations; your app may not work properly until they are applied.

Run the following command to apply:

```
python manage.py migrate
```

Changing the port.  

By default, the runserver command starts the development server on the internal IP at port 8000.  

```
py manage.py runserver 8080
```

&nbsp;  

[Django documentation](https://docs.djangoproject.com/en/4.0/intro/tutorial01/)


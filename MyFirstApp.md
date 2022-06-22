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

### Writing first view

Let’s write the first view. Open the file **polls/views.py** and put the following Python code in it:

```
from django.http import HttpResponse


def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")
```

This is the simplest view possible in Django. To call the view, we need to map it to a URL - and for this we need a URLconf.  
To create a URLconf in the polls directory, create a file called urls.py  

In the polls/urls.py file include the following code:  
```
from django.urls import path

from . import views

urlpatterns = [
    path('', views.index, name='index'),
]
```

You have now wired an index view into the URLconf. Verify it’s working with the following command:
```
py manage.py runserver
```

`If you get an error page here, check that you’re going to http://localhost:8000/polls/ and not http://localhost:8000/.`

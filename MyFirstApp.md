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
The next step is to point the root URLconf at the polls.urls module. In mysite/urls.py, add an import for django.urls.include and insert an include() in the urlpatterns list, so you have:  

`mysite/urls.py`

```
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('polls/', include('polls.urls')),
    path('admin/', admin.site.urls),
]
```
When to use include() [^1] function.
[^1]: You should always use include() when you include other URL patterns. admin.site.urls is the only exception to this.

The path()[^2][^3] function.
[^2]: The path() function is passed four arguments, two required: route and view, and two optional: kwargs, and name


[^3]: path() argument.  

    path() argument: route  
    &nbsp; &nbsp; route is a string that contains a URL pattern. When processing a request, Django starts at the first pattern in urlpatterns and makes its way down the list,comparing the requested URL against each pattern until it finds one that matches.
    
    path() argument: view  
    &nbsp; &nbsp; When Django finds a matching pattern, it calls the specified view function with an HttpRequest object as the first argument and any “captured” values from the      route as keyword arguments.
    

You have now wired an index view into the URLconf. Verify it’s working with the following command:
```
py manage.py runserver
```

`If you get an error page here, check that you’re going to http://localhost:8000/polls/ and not http://localhost:8000/.`

&nbsp;  

[django documentation](https://docs.djangoproject.com/en/4.0/intro/tutorial01/#id3)




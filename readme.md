# Django Reference
## Build a Django project step-by-step

### How to use this repository
View the files for each step by selecting from the branches dropdown.

### Step one: Create a project directory
* Create a project directory on the hard drive.
* Navigate to the project folder in the terminal

### Step two: Start the Django project
From the project folder execute
```
$ django-admin startproject djangoweb
```
This creates a project folder containing a **Django App**

### Step three: Navigate to project folder
* Set path to new project folder
* Open project folder in text editor

### Step four: Add URLS to urls.py and create views.py
* Once sitemap is complete update the urls.py file in the djangoweb(main) directory.
* This is the main directory of the project.

1. import Django's url module using:
```python
from django.conf.urls import url
```
2. pass the url suffixes and the associated views.py methods into the url object in the urlpatterns list
3. Create a views.py file in the current directory
4. import views.py file in the current app directory
```python
from . import views
```

The urls.py should look like this:

```python
from django.contrib import admin
from django.urls import path
from django.conf.urls import url
from . import views

urlpatterns = [
    url(r'^admin/', admin.site.urls),
    url(r'^$', views.homepage),
    url(r'^about/$', views.about),
]
```
> Note: Any modules referenced in a file must first be imported to that file

### Step five: Define request return statements in views.py
1. Start by importing the HttpResponse module from django.http
2. Then import the render module from django.shortcuts
3. Define a function for each URL created, naming accordingly.
4. Test the urls and views linkages using a simple HttpResponse passing a string

This is what the code should look like:

```python
from django.http import HttpResponse
from django.shortcuts import render

def homepage(request):
  return HttpResponse("homepage")

def about(request):
  return HttpResponse("about")

```

# django_resumido

python3.9 -m venv venv <br>
source venv/bin/activate <br>
pip install Django==3.2.8 <br>
django-admin startproject sys_email . <br>


## settings.py
```
TIME_ZONE = 'America/Sao_Paulo'
LANGUAGE_CODE = 'pt-BR'
STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'static')
ALLOWED_HOSTS = ['127.0.0.1']
```

## comando
```
python manage.py startapp home 
python manage.py migrate 
python manage.py makemigrations 

```

<br><br>

## settings.py
```
INSTALLED_APPS = [ 
    'django.contrib.admin', 
    'django.contrib.auth',  
    'django.contrib.contenttypes',  
    'django.contrib.sessions',  
    'django.contrib.messages',  
    'django.contrib.staticfiles',  
    'home',  
]  
```

## sys_mail/urls.py

```
from django.contrib import admin 
from django.urls import path, include 

urlpatterns = [  
    path('admin/', admin.site.urls), 
    path('', include('home.urls')),  
]  
```

## home/urls.py
```
from django.urls import path  
from . import views  

urlpatterns = [  
    path('', views.post_list, name='post_list'),  
]  

```


## home/view.py
```
def post_list(request):  
    return render(request, 'home/post_list.html', {})  
```	
	
## home/templates/blog/post_list.html

```
<html>  
<body>
    <p>Hi there!</p>
    <p>It works!</p>
</body>
</html>
```

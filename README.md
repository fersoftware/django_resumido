# django_resumido

python3.9 -m venv venv <br>
source venv/bin/activate <br>
pip install Django==3.2.8 <br>
django-admin startproject sys_email . <br>


## settings.py
TIME_ZONE = 'America/Sao_Paulo'<br>
LANGUAGE_CODE = 'pt-BR'<br>
STATIC_URL = '/static/'<br>
STATIC_ROOT = os.path.join(BASE_DIR, 'static')<br>
ALLOWED_HOSTS = ['127.0.0.1']<br>

## comando
python manage.py startapp home <br>
python manage.py migrate <br>
python manage.py makemigrations <br>

<br><br>

## settings.py

INSTALLED_APPS = [ <br>
    'django.contrib.admin', <br>
    'django.contrib.auth',  <br>
    'django.contrib.contenttypes',  <br>
    'django.contrib.sessions',  <br>
    'django.contrib.messages',  <br>
    'django.contrib.staticfiles',  <br>
    'home',  <br>
]  <br>


## sys_mail/urls.py
from django.contrib import admin <br>
from django.urls import path, include <br>

urlpatterns = [  <br>
    path('admin/', admin.site.urls),  <br>
    path('', include('home.urls')),  <br>
]  <br>


## home/urls.py
from django.urls import path  <br> 
from . import views  <br>

urlpatterns = [  <br>
    path('', views.post_list, name='post_list'),  <br>
]  <br>


## home/view.py
def post_list(request):  <br>
    return render(request, 'home/post_list.html', {})  <br>
	
	
## home/templates/blog/post_list.html
'
<html>  
<body>
    <p>Hi there!</p>
    <p>It works!</p>
</body>
</html>
'

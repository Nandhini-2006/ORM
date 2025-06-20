# Ex02 Django ORM Web Application
## Date: 

## AIM
To develop a Django application to store and retrieve data from a Movies Database using Object Relational Mapping(ORM).

## ENTITY RELATIONSHIP DIAGRAM



## DESIGN STEPS

### STEP 1:
Clone the problem from GitHub

### STEP 2:
Create a new app in Django project

### STEP 3:
Enter the code for admin.py and models.py

### STEP 4:
Execute Django admin and create details for 10 books

## PROCEDURE AND PROGRAM

Creating Repository:

First, a path to make a folder where git needs to be created is identified.
```
Fork the repository (https://github/gowriganeshns/django-orm-app)
```
Clone the repository
```
git clone https://github.com/gauthamkrishna7/django-orm-app
```
After cloning the folder with the repository name django-orm-app will be created
Inside django-orm-app:

Write the following commands
```
cd django-orm-app
django-admin startproj myproj
```
Then move into the folder myproj where manage.py file is located. Now give the commands to create myapp
```
python3 manage.py startapp myapp
```
Then change the necessary settings in the settings.py.
```
from pathlib import Path
import os
ALLOWED_HOSTS = ['*']
INSTALLED_APPS = [
  'django.contrib.admin',
  'django.contrib.auth',
  'django.contrib.contenttypes',
  'django.contrib.sessions',
  'django.contrib.messages',
  'django.contrib.staticfiles',
  'myapp'
 ]
STATICFILES_DIR=[
  os.path.join(BASE_DIR,'static')
 ]
```
Create a Super User:


```
python3 manage.py makemigrations
python3 manage.py migrate
python3 manage.py createsuperuser
```
Enter the admin and password according to your preferences.

You will receive the command Superuser successfully created.

Visit the admin app at (http://127.0.0.1:8000/admin) and log in with the superuser account that you have created:

Write the code: - Write the given codes in models.py and admin.py

Run the code: - Make migrations python3 manage.py makemigrations myapp   

python3 manage.py migrate myapp -

In the admin interface (http://127.0.0.1:8000/admin) following web interface will be obtained. - 

Now add 10 employee details having only 5 post.

PROGRAM

```
models.py

from django.db import models
from django.contrib import admin

class Student(models.Model):
    referencenumber=models.CharField(max_length=20,help_text="refernce number")
    name=models.CharField(max_length=100)
    age=models.IntegerField()
    email=models.EmailField()
    phonenumber=models.IntegerField()

class StudentAdmin(admin.ModelAdmin):
    list_display=('referencenumber','name','age','email','phonenumber')

class Employee (models.Model):
    emp_id=models.CharField(primary_key=True,max_length=4,help_text='Employee ID')
    ename=models.CharField(max_length=50)
    post=models.CharField(max_length=20)
    salary=models.IntegerField()

class EmployeeAdmin(admin.ModelAdmin):
    list_display=('emp_id','ename','post','salary')
```
```
admin.py

from django.contrib import admin
from .models import Student,StudentAdmin,Employee,EmployeeAdmin
# Register your models here.
admin.site.register(Student,StudentAdmin)
admin.site.register(Employee,EmployeeAdmin)

```
## OUTPUT

![Screenshot 2025-06-20 193051](https://github.com/user-attachments/assets/0b31080b-0c97-4d3c-86d1-01f0312df6c1)



## RESULT
Thus the program for creating movies database using ORM hass been executed successfully

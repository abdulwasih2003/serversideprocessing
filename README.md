# Design a Website for Server Side Processing

## AIM:
To design a website to perform mathematical calculations in server side.

## DESIGN STEPS:

### Step 1:
Design your website for calculation using wireframe work.
### Step 2:
Then to execute the wireframe work design use HTML,CSS.
### Step 3:
Use views.py to execute the coding in server side.
### Step 4:
Mention the path of the website in urls.py.
### Step 5:
Publish the website in the given URL.

## PROGRAM :

## Area.html:
~~~
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <meta http-equiv='X-UA-Compatible' content='IE=edge'>
    <title>Math Calculation</title>
    <meta name='viewport' content='width=device-width, initial-scale=1'>
    <script src='main.js'></script>
    <style>
        * {
  box-sizing: border-box;
  font-family: Arial, Helvetica, sans-serif;
}
body {
  background-image: url("./static/img/bg.jpg");
  width: fit-content;
  height:fit-content
  margin-left: auto;
  margin-right: auto;
}

.container {
  width: 1080px;
  margin-left: auto;
  margin-right: auto;
  padding-top: 200px;
  padding-left: 300px;
  opacity: 0.6;
}
.content {
  display:block;
  width: 500px;
  min-height: 300px;
  font-size: 20px;
  background-color:white;
}
h1{
    color: rgb(16, 17, 17);
    text-align: center;
    padding-top: 25px;
    font-weight: bolder;
}
.formelement{
    color: black;
    text-align: center;
    margin-top: 5px;
    margin-bottom: 5px;
    font-weight: bolder;
}
    </style>
</head>
<body>
    <div class="container">
    <div class="content">
    <h1>Area of Triangle</h1>
    <form method="POST">
        
        <div class="formelement">
        Length : <input type="text" name="Base" value=""></input> Meters<br/>
        </div>
        <div class="formelement">
        Height : <input type="text" name="Height" value=""></input> Meters<br/>
        </div>
        
        <div class="formelement">
        <input type="submit"  value="Calculate Area"></input><br/>
        </div>
        <div class="formelement">
        Area : <input type="text" name="Area" value=""></input> Meter<sup>2</sup><br/>
        </div>
        <br>
        <div class="formelement">
          <B><center>Developed by : Syed Abdul Wasih H </center></B> 
          </div>
    
    </form>
    </div>
    </div>
</body>
</html>
~~~
## Views.py:
~~~
from django.shortcuts import render
def volumecalculation(request):
    context={}
    context['b'] = "0"
    context['h'] = "0"
    context['area'] = "0"
    
    if request.method == 'POST':
        b = request.POST.get('base','0')
        h = request.POST.get('height','0')
        
        area =(int(b)*int(h))/2
        context['b'] = b
        context['h'] = h
        context['area'] = area
  
    return render(request,'area.html',context)
~~~
## Urls.py:
~~~
"""calculation URL Configuration

The `urlpatterns` list routes URLs to views. For more information please see:
    https://docs.djangoproject.com/en/3.1/topics/http/urls/
Examples:
Function views
    1. Add an import:  from my_app import views
    2. Add a URL to urlpatterns:  path('', views.home, name='home')
Class-based views
    1. Add an import:  from other_app.views import Home
    2. Add a URL to urlpatterns:  path('', Home.as_view(), name='home')
Including another URLconf
    1. Import the include() function: from django.urls import include, path
    2. Add a URL to urlpatterns:  path('blog/', include('blog.urls'))
"""

from django.contrib import admin
from django.urls import path
from mathapp import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('areaofrect/',views.areacalc,name="areaofrect"),
    path('',views.areacalc,name="areaofrect")]

~~~

## OUTPUT:
![Output](1.png)

## Result:
A website to perform mathematical calculations in server side is created.

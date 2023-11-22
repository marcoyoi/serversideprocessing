# Design a Website for Server Side Processing

## AIM:
To design a website to perform mathematical calculations in server side.

## DESIGN STEPS:

### Step 1:

Desing your website for calculation using wireframe work

### Step 2:

Then to execute the wireframe work desing use html,cs

### Step 3:

Then to execute the wireframe work desing use html,cs

### Step 4:

Mention the path of the website in urls.py

### Step 5:

Publish the website in the given URL


### Step 6:

Publish the website in the given URL.

## PROGRAM :
## math.html
```html 
<html>
<head>
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=edge'>
<title>Area of Prism</title>
<meta name='viewport' content='width=device-width, initial-scale=1'>
<style type="text/css">
body 
{
background-color:cyan;
}
.edge {
width: 1080px;
margin-left: auto;
margin-right: auto;
padding-top: 200px;
padding-left: 300px;
}
.box {
    display:block;
border: Thick dashed lime;
width: 500px;
min-height: 300px;
font-size: 20px;
background-color: purple;
}
.formelt{
color: Red;
text-align: center;
margin-top: 5px;
margin-bottom: 5px;
}
h1
{
    color: yellow;
text-align: center;
padding-top: 20px;
}
</style>
</head>
<body>
    <div class="edge">
    <div class="box">
    <h1>Area of a Prism</h1>
    <form method="POST">
    {% csrf_token %}
    <div class="formelt">
    Length : <input type="text" name="side" value="{{s}}"></input>(in m)<br/>
    </div>
    <div class="formelt">
    Breadth : <input type="text" name="height" value="{{h}}"></input>(in m)<br/>
    </div>
    <div class="formelt">
    <input type="submit" value="Calculate"></input><br/>
    </div>
    <div class="formelt">
        Area : <input type="text" name="area" value="{{area}}"></input>m<sup>2</sup><br/>
    </div>
    </form>
    </div>
    </div>
</body>
</html>        
```
## views.py
```py
from django.shortcuts import render
from django.template  import loader
from django.shortcuts import render
# Create your views here.




def prismarea(request):
    context={}
    context['area'] = "0"
    context['s'] = "0"
    context['h'] = "0"
    if request.method == 'POST':
        print("POST method is used")
        s = request.POST.get('side','0')
        h = request.POST.get('height','0')
        print('request=',request)
        print('side=',s)
        print('height=',h)
        area = 2*int(s) * int(s)+4*int(s)*int(h)
        context['area'] = area
        context['s'] = s
        context['h'] = h
        print('Area=',area)
    return render(request,'myapp/math.html',context)

```
## urls.py
```py
from django.contrib import admin
from django.urls import path
from myapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    
    path('areaofprism/',views.prismarea,name="areaofprism"),
]
```
## OUTPUT:

![image](https://github.com/marcoyoi/serversideprocessing/assets/128804366/64673793-2898-4670-afb5-0fe1aa7b38a4)

### Home Page:

![WhatsApp Image 2023-11-22 at 13 29 23_81ea33f4](https://github.com/marcoyoi/serversideprocessing/assets/128804366/855033bc-de76-4e77-8917-01ac9254de83)

## Result:
the program is executed succssfully

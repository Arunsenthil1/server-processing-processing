# Ex.05 Design a Website for Server Side Processing
# Date:02/12/2024
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
math.html

<html>
<head>
<h1 align=	"center"> S DHANUS KARTHI (24005701)</h1>
<title>Area of Rectangle</title>
<style>
    body {
        background-color: red;
    }
    .edge {
        width: 1240px;
        margin-left: auto;
        margin-right: auto;
        padding-top: 200px;
        padding-left: 200px;
    }
    .box { 
        display: block;
        width: 500px;
        min-height: 30px;
        font-size: 20px;
        background-color: yellow;
        color: black;
        text-align: center;
        padding-top: 20px;
        padding-bottom: 20px;
    }
    .formelt {
        margin-top: 7px;
        margin-bottom: 6px;
    }
</style>
</head>
<body>
<div class="edge">
    <div class="box">
        <h1>Area of a Rectangle</h1>
            <div>
                Length: <input type="text" name="length" value="1"> (in m)<br/>
            </div>
            <div>
                Breadth: <input type="text" name="breadth" value="1"> (in m)<br/>
            </div>
            <div class="formlet">
                <input type="submit" value="Calculate"><br/>
            </div>
            <div class="formelt">
               
            </div>
    </div>
</div>
</body>
</html>

views.py

from django.shortcuts import render
def powerlamp(request): 
context={} 
context['power']="0" 
context['i']="0" 
context['r']="0" 
if request.method=='POST': 
    print("POST method is used")
    i=request.POST.get('intensity','0')
    r=request.POST.get('resistance','0')
    print('request=',request) 
    print('intensity=',i) 
    print('resistance=',r) 
    power=(int(i) ** 2 ) * int(r) 
    context['power']=power
    context['i']=i
    context['r']=r 
    print('Power=',power) 
     return render(request,'myapp/math.html',context)

urls.py

from django.contrib import admin 
from django.urls import path 
from myapp import views 
urlpatterns = [ 
path('admin/', admin.site.urls), 
path('powerlamp/',views.powerlamp,name="powerlamp"),
path('',views.powerlamp,name="powerlamproot")
]
```
# SERVER SIDE PROCESSING:![Screenshot 2024-12-02 193137](https://github.com/user-attachments/assets/878cf5b0-d52e-417f-9056-6d2857c0121f)


# HOMEPAGE:![Screenshot 2024-12-02 193234](https://github.com/user-attachments/assets/fdfa287f-d28e-4c1e-8207-7d8fa75da9d0)


# RESULT:
The program for performing server side processing is completed successfully.

# Ex.05 Design a Website for Server Side Processing
# Date:30/10/2024
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
<html>

<head>
    <meta charset='utf-8'>
    <meta http-equiv='X-UA-Compatible' content='IE=edge'>
    <title>POWER OF LAMP IN INCANDESCENT BULD</title>
    <meta name='viewport' content='width=device-width, initial-scale=1'>
    <style type="text/css">
        body {
            background-color:white;
        }

        .edge {
            display: flex;
            height: 100vh;
            width: 100%;    
            justify-content: center;
            align-items: center;
        }

        .box {
            display: block;
            width: 500px;
            min-height: 300px;
            font-size: 20px;
            background: rgb(33, 19, 163);
            background: linear-gradient(90deg, rgb(106, 62, 215) 9%, rgb(57, 25, 173) 56%);
            border-radius: 10px;
            box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
            font-style: oblique;
        }

        .formelt {
            color: rgb(0, 0, 0);
            text-align: center;
            margin-top: 7px;
            margin-bottom: 6px;
        }

        h1 {
            color: rgb(0, 0, 0);
            text-align: center;
            padding-top: 20px;
        }
        input{
            margin: 5px;
            padding: 5px;
            border-radius: 5px;
            border: none;

        }
    </style>
</head>

<body>
    <div class="edge">
        <div class="box">
            <h1>POWER OF LAMP IN INCANDESCENT BULB</h1>
            <form method="POST">
                {% csrf_token %}
                <div class="formelt">
                    Intensity : <input type="text" name="Intensity" value="{{I}}"></input>(in A)<br />
                </div>
                <div class="formelt">
                    Resistence : <input type="text" name="Resistence" value="{{R}}"></input>(in Ω)<br />
                </div>
                <div class="formelt">
                    <input type="submit" value="Calculate"></input><br />
                </div>
                <div class="formelt">
                    Power : <input type="text" name="Power" value="{{Power}}"></input>W<br />
                </div>
            </form>
        </div>
    </div>
</body>

</html>
```
# SERVER SIDE PROCESSING:
```
def powerlamp(request):
    context={}
    context['Power'] = ""
    context['I'] = ""
    context['R'] = ""
    if request.method == 'POST':
        print("POST method is used")
        I = request.POST.get('Intensity','')
        R = request.POST.get('Resistence','')
        print('request=',request)
        print('Intensity=',I)
        print('Resistence=',R)
        Power = int(I) * int(I) * int(R)
        context['Power'] = Power
        context['I'] = I
        context['R'] = R
        print('Power=',Power)
    return render(request,'experiment5.html',context)
```
# HOMEPAGE:
![EXPERIMENT 5 SS](https://github.com/user-attachments/assets/6747ce37-3e82-4515-8456-38d6e95a8968)
# OUTPUT:

![EXPERIMENT 5 SS (1)](https://github.com/user-attachments/assets/21afc962-b6e2-4248-9497-75f6831b48f1)

# RESULT:
The program for performing server side processing is completed successfully.

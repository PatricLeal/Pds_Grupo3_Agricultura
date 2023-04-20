# [Django Material Dashboard](https://appseed.us/product/material-dashboard/django/)

Open-source **Django** project crafted on top of **[Material Dashboard](https://appseed.us/product/material-dashboard/django/)**, an open-source `Boostrap 5` design from [Creative-Tim](https://www.creative-tim.com/?AFFILIATE=128200)
The product is designed to deliver the best possible user experience with highly customizable feature-rich pages. `Material Material` has easy and intuitive responsive design whether it is viewed on retina screens or laptops.
Manual Build
👉 Download the code

$ git clone https://github.com/app-generator/django-material-dashboard.git
$ cd django-material-dashboard

👉 Install modules via VENV

$ virtualenv env
$ source env/bin/activate
$ pip install -r requirements.txt

👉 Set Up Database

$ python manage.py makemigrations
$ python manage.py migrate

👉 Create the Superuser

$ python manage.py createsuperuser

👉 Start the app

$ python manage.py runserver
At this point, the app runs at http://127.0.0.1:8000/.


Codebase structure
The project is coded using a simple and intuitive structure presented below:

< PROJECT ROOT >
   |
   |-- core/                            
   |    |-- settings.py                  # Project Configuration  
   |    |-- urls.py                      # Project Routing
   |
   |-- home/
   |    |-- views.py                     # APP Views 
   |    |-- urls.py                      # APP Routing
   |    |-- models.py                    # APP Models 
   |    |-- tests.py                     # Tests  
   |    |-- templates/                   # Theme Customisation 
   |         |-- includes                # 
   |              |-- custom-footer.py   # Custom Footer      
   |     
   |-- requirements.txt                  # Project Dependencies
   |
   |-- env.sample                        # ENV Configuration (default values)
   |-- manage.py                         # Start the app - Django default start script
   |
   |-- ************************************************************************

How to Customize
When a template file is loaded, Django scans all template directories starting from the ones defined by the user, and returns the first match or an error in case the template is not found. The theme used to style this starter provides the following files:

# This exists in ENV: LIB/admin_material
< UI_LIBRARY_ROOT >                      
   |
   |-- templates/                     # Root Templates Folder 
   |    |          
   |    |-- accounts/       
   |    |    |-- login.html           # Sign IN Page
   |    |    |-- register.html        # Sign UP Page
   |    |
   |    |-- includes/       
   |    |    |-- footer.html          # Footer component
   |    |    |-- sidebar.html         # Sidebar component
   |    |    |-- navigation.html      # Navigation Bar
   |    |    |-- scripts.html         # Scripts Component
   |    |
   |    |-- layouts/       
   |    |    |-- base.html            # Masterpage
   |    |    |-- base-auth.html       # Masterpage for Auth Pages
   |    |
   |    |-- pages/       
   |         |-- index.html           # Dashboard Page
   |         |-- profile.html         # Profile Page
   |         |-- *.html               # All other pages
   |    
   |-- ************************************************************************
When the project requires customization, we need to copy the original file that needs an update (from the virtual environment) and place it in the template folder using the same path.

For instance, if we want to customize the footer.html these are the steps:

✅ Step 1: create the templates DIRECTORY inside the home app
✅ Step 2: configure the project to use this new template directory
core/settings.py TEMPLATES section
✅ Step 3: copy the footer.html from the original location (inside your ENV) and save it to the home/templates DIR
Source PATH: <YOUR_ENV>/LIB/admin_material/template/includes/footer.html
Destination PATH: <PROJECT_ROOT>home/templates/includes/footer.html
To speed up all these steps, the codebase is already configured (Steps 1, and 2) and a custom footer can be found at this location:

home/templates/includes/custom_footer.html

By default, this file is unused because the theme expects footer.html (without the custom- prefix).

In order to use it, simply rename it to footer.html. Like this, the default version shipped in the library is ignored by Django.

In a similar way, all other files and components can be customized easily.


Deploy on Render
Create a Blueprint instance
Go to https://dashboard.render.com/blueprints this link.
Click New Blueprint Instance button.
Connect your repo which you want to deploy.
Fill the Service Group Name and click on Update Existing Resources button.
After that your deployment will start automatically.
At this point, the product should be LIVE.


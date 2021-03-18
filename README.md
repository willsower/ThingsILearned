# ThingsILearned
Just an area where I put things I learned

### March 18, 2021

Learned a lot about Django architecture with overall project and app folders. Refer to this document written by Muhammad [link](https://muhammadraza.me/2019/Creating-Simple-WebApp-Using-Django/)

### March 17, 2021

Created Django project with subapp.

1. Start django project (after django has been downloaded and pipenv has started) `django-admin.py startproject termtext`
2. `cd termtext`
3. Create app `python3 manage.py startapp termtext_frontend`
4. To run the server `./manage.py runserver`
5. We want to use DB - SQLite, so we want to create the migrations `./manage.py migrate`
6. To create a super user for the app run `./manage.py createsuperuser` which allows me to create admin user name / password
7. Running the server again `./manage.py runserver` I can put /admin in the URL and sign in with my super user credentials

### March 16, 2021
Create an environment in terminal by using export, for example if I wanted to create an environment variable called email and set it, I would do the following command.

`export EMAIL=myemail@gmail.com`

To read the variable I could do 

`echo $EMAIL`

I also made this in the bash mini shell, but I forgot how to do it myself haha

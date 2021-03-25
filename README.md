# ThingsILearned
Just an area where I put things I learned

### March 25, 2021

To create your own server in the directory you use the command `python3 -m http.server` you can then access this server on your local laptop by going to `localhost:8000`.

To access this on a phone or another computer that is on the same network, you would get your IP address, and in a browser would be `<IPAddress>:8000` where the port is 8000.

### March 20, 2021

1. I have learned about SMTP gateway and IMAP gateway. SMTP is Simple Mail Transfer Protocol allowing you to receive messages. While IMAP is Internet Message Access Protocol allowing us to get the email. I wrote a script to get user's emails here. This github project which I'm working on with Muhammad allows us to send and recieve messages from text with an email. Click [here](https://github.com/mtdevss/terminal-text)

2. In Discord you can do
"``<name of the language>
Put your code here 

``"
To get different colors of your code to render.

### March 18, 2021

1. Learned a lot about Django architecture with overall project and app folders. Refer to this document written by Muhammad [link](https://muhammadraza.me/2019/Creating-Simple-WebApp-Using-Django/)

2. Learned how to add React App and some components inside of a Django Rest Framework

- cd into main folder
- Create new app `django-admin startapp frontend`
- cd into frontend folder
- Inside of frontend folder, create `templates` directory and `static` directory
- In `templates` directory create folders `css`, `js`, and `images`
- Inside of your frontend folder create directory `src` then add directory `components` into src
- Inside of the frontend directory, create a node project `npm init -y`
- Install webpack `npm i webpack webpack cli --save-dev` This package will take all our javascript and bundle it in one single js file
- Install bable `npm i @babel/core babel-loader @babel/preset-env @babel/preset-react --save-dev` Essentially what babel does is it takes our JavaScript and code and makes sure it is compatable with other browsers. 
- Install react `npm i react react-dom --save-dev`
- Install materialUI `npm install @material-ui/core` built in components for us so we don't have to build everything (cards/grids) like boostrap
- Install another plugin for babel `npm install @babel/plugin-proposal-class-properties` this is so we can use async, wait, etc commands in our JavaScript
- Install plugin for react `npm install react-router-dom` will let us to re route our pages
- Install plugin for materialUI `npm install @material-ui/icons` Get icons for material ui

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

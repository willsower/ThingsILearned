# ThingsILearned

Just an area where I put things I learned

### July 21, 2021

##### UserData for Mock EC2 Linux Instance

```Bash
#!/bin/bash

########################################
##### USE THIS WITH AMAZON LINUX 2 #####
########################################

# get admin privileges
sudo su

# install httpd (Linux 2 version)
yum update -y
yum install -y httpd.x86_64
systemctl start httpd.service
systemctl enable httpd.service
echo "Hello World from $(hostname -f)" > /var/www/html/index.html
```

##### Create SSH Key for GitHub

1. In Mac install git
2. Set username `git config --global user.name "willsower"`
3. Set email `git config --global user.email "jatr812@gmail.com`
4. Create SSH Key `ssh-keygen -t rsa -C "jatr812@gmail.com"`. Follow necessary steps for generation
5. Copy the SSH key `pbcopy < ~/.ssh/id_rsa.pub`
6. Go into GitHub and go to AccountSettings -> SSH Keys -> Add SSH Key
7. Add label, paste the public key in the big text box
8. To test, run `ssh -T git@github.com`

### June 24, 2021

##### Delete branches
```GIT
// delete branch locally
git branch -d localBranchName

// delete branch remotely
git push origin --delete remoteBranchName
```

### April 20, 2021

##### SSH into WWU Machines + Using SCP to copy files from virtual machine to personal machine

`ssh -p 922 ${username}@linux.cs.wwu.edu` to ssh into school machines

`scp -P 922 ${username}@linux.cs.wwu.edu:~/document.txt ~/Documents/` to copy files from my VM to my personal Documents directory on my local machine.

For my sake, grabbing LaTeX files I use `scp -P 922 rosej25@linux.cs.wwu.edu:/projects/49x/tex2speech/texFiles/computer.tex ~/Documents/` command

This is for me to get to my tex2speech logs `scp -P 922 rosej25@linux.cs.wwu.edu:~/CSCI/Tex2Speech/latex2speech/tex2speech/log.log ~/Documents/`

### April 7, 2021

###### Uploading Flask App to Elastic Beanstalk

After creating a virtual environment, and having my requirements in requirements.txt. My folder structure should look something similiar:
`project/
  venv
  app.py
  requirements.txt`
  
 If you run `python3 app.py` it should run locally
 
 Before proceding, make sure you have the AWS CLI `pip3 install awscli` then download the elastic beanstalk CLI `pip3 install awsebcli` If you type `aws` in the terminal you can see the AWS CLI was downloaded successfully, along if you type `eb` in the terminal you can see that that was downloaded successfully too.
 
 In the command line, to create an elastic beanstalk application run `eb init -p python-3.6 projectName --region us-east-1`
 
 Now to setup the configuration type `eb init` which will prompt you to add a keypair so that you can connect to your EC2 instance through SSH. If you ever need to change this information in the future run `eb init -i`
 
 Create an environment and deploy the application with `eb create flask-env` command, this could take about 5 minutes to create all the resources.
 
 To open your application run `eb open`
 
 If you ever need to completely delete everything on elastic beanstalk run `eb terminate flask-env`
 
 if you ever need to redeploy your code to the same application run `eb deploy` in the repository

### April 2, 2021

An easier virtual environment to use is `pipenv`

To create a shell
- `pipenv shell`

To download dependencies in PipFile (similiar to requirements.txt)
- `pipenv install`

Sometimes when running `pipenv shell` it doesn't know where Python3.6 is. To find this, type `python` or `python3` in terminal
- Type `import sys` then enter
- Type `print(sys.executable)` to get the path. Copy the path and get out of python interpreter

In regular terminal type `pipenv --python <path_to_python>`

### April 1, 2021

To setup a temporary virtual environment the following commands are
- `python3 -m venv env`
- `source env/bin/activate`

This creates a env/ folder so in `.gitignore` be sure to add `env/`

After creating the environment, if you want to add installed libraries to the `requirements.txt` file run the following command
- `python3 -m pip freeze > requirements.txt`

To download all items in your requirements.txt file run the following command
- `pip install -r requirements.txt`

### March 31, 2021

To create a Next.JS project write this command in your terminal `npx create-next-app nextjs-blog --use-npm --example "https://github.com/vercel/next-learn-starter/tree/master/learn-starter"` for a basic layout. You need to have `node.js` installed

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

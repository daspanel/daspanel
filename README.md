# Daspanel - WIP

This is the first version of Daspanel. It is an exciting step forward towards 
making an hosting control panel using Docker. We created it so that you can 
create any site, plain or using PHP, in your local machine and when ready easy 
deploy it on an public server exactly as you see it in the development machine.

Build something great!

* Free software: MIT license
* Documentation: <https://daspanel.github.io>

Warning: This is an early stage project with a lot of bug's.

## How to test

1) Download and unzip the project zip file from 
https://github.com/daspanel/daspanel/archive/master.zip

2) Get a Daspanel UUID for your test. This UUID must be of the type 
[CUID](https://github.com/ericelliott/cuid)
* You can get one online using [getuuid.com](http://getuuid.com)
* Or, download the contents of 
[GETUUID Project](https://github.com/daspanel/getuuid.github.io)
, unzip it and open the index.html file in your browser (it's the source code 
of getuuid.com).

3) Edit the daspanel.env file and set:
* DASPANEL_GUUID = the UUID you obtained earlier
* DASPANEL_MASTER_PASSWORD = The password you want to use as admin
* DASPANEL_MASTER_EMAIL = your email. It will be used to login to the panel and as recipient of notifications messages

4) Edit the smtp.env file and modify:
* DASPANEL_MAIL_SERVER = the SMTP server address. Must be in server.com:port format
* DASPANEL_MAIL_USER = the user is used to log in to the SMTP server. Normally something like user@domain.com
* DASPANEL_MAIL_PWD = the user's password on the SMTP server.

5) Open an shell and go to the directory where is the file docker-compose.yml

6) Run this command and wait until Docker download's all container's images needed by Daspanel:
```shell
docker-compose up -d
```

7) Open this URL in your browser: http://admin.daspanel.site
* daspanel.site is an domain that always resolve any address to 127.0.0.1. 
Using it you dont need to change your computar host file to use Daspanel in 
your local computer.

8) use the values of DASPANEL_MASTER_EMAIL and DASPANEL_MASTER_PASSWORD to login in the control panel GUI

9) Go to the site modules and add new site using the "+" icone.
* Write an description for your new site
* Choose 'Grav' as Type
* And 'PHP 7.0' as Engine

10) After saved this new site, install some content on it using the displayed 
form:
* If this new site is of the type 'Grav' put in the form field 'URL' this 
address: https://getgrav.org/download/core/grav-admin/1.1.17

11) If all goes fine you can click in the preview button of the site and got in 
a new browser window the newly created Grav site. Enjoy!

12) Every site is a card, in every card you have basic comamand's like edit, 
preview and delete. Every card can have one or more slide's like About, Control, 
Versions, Redirects, etc, and you can navigate in each slide using horizontal nav list 
just above the footer of the slide.

### If you want to create a wordpress website follow these steps: ###

1) Go to the site modules and add new site using the "+" icone.
* Write an description for your new site
* Choose 'Wordpress' as Type
* And 'PHP 7.0' as Engine

2) After saved this new site, install some content on it using the displayed 
form:
* Put in the form field 'URL' this 
address: http://wordpress.org/latest.zip

3) In another browser window open this URL: http://adminer.svc.daspanel.site

4) Login in Adminer with:
* Server = daspanel-mariadb
* User = root
* Password = The value you set in DASPANEL_MASTER_PASSWORD on the daspanel.env file

5) Create new DB for Wordpress

6) Back to the daspanel site list click on the Preview buttom of the Wordpress site

7) Complete the Wordpress setup. Remember, teh database server is 'daspanel-mariadb'

8) Back to the sites list in Daspanel click on the Previe


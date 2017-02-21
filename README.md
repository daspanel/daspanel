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
https://github.com/daspanel/panel/archive/master.zip

2) Get a Daspanel UUID for your test. This UUID must be of the type 
[CUID](https://github.com/ericelliott/cuid)
* You can get one online via [CUID](http://getuuid.com)
* Or, download the contents of 
[GETUUID Project](https://github.com/daspanel/getuuid.github.io/archive/master.zip)
, unzip it and open the index.html file in your browser (it's the source code 
of getuuid.com).

3) Edit the daspanel.env file and modify:
A) DASPANEL_GUUID = the UUID you obtained earlier
B) DASPANEL_MASTER_PASSWORD = The password you want to use as admin
C) DASPANEL_MASTER_EMAIL = your email. It will be used to login to the panel and as recipient of notifications messages

4) Edit the smtp.env file and modify:
A) DASPANEL_MAIL_SERVER = the SMTP server address. Must be in server.com:port format
B) DASPANEL_MAIL_USER = the user is used to log in to the SMTP server. Normally something like user@domain.com
C) DASPANEL_MAIL_PWD = the user's password on the SMTP server.

5) Open an shell and go to the directory where is the file docker-compose.yml

6) Run this command and wait until Docker download's all container's images needed by Daspanel:
```shell
docker-compose up -d
```

7) Open this URL in your browser: http://admin.daspanel.site

8) use the values of DASPANEL_MASTER_EMAIL and DASPANEL_MASTER_EMAIL to login in the control panel GUI

9) Go to the site modules and add new site using the "+" icone.

10) Install content in the new site using the displayed

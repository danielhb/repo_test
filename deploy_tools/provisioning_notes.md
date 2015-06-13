Provisioning a new site
=======================

## Required packages:

* nginx
* Python 3
* Git
* pip
* virtualenv

eg, on Ubuntu:

    sudo apt-get install nginx git python3 python3-pip
    sudo pip3 install virtualenv

## Nginx Virtual Host config

* see nginx.template.conf
* replace SITENAME with, eg, staging.my-domain.com
eg sed command:
sed "s/SITENAME/theciceroni.com/g" deploy_tools/nginx_template.conf | sudo tee /etc/nginx/sites-available/theciceroni.com


## Upstart Job

* see gunicorn-upstart.template.conf
* replace SITENAME with, eg, staging.my-domain.com
eg sed command:
sed "s/SITENAME/theciceroni.com/g" deploy_tools/gunicorn-upstart.template.conf | sudo tee /etc/init/gunicorn-theciceroni.com.conf



## Folder structure:
Assume we have a user account at /home/username

/home/username
└── sites
    └── SITENAME
         ├── database
         ├── source
         ├── static
         └── virtualenv

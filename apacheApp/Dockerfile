# TITLE: WebApp
# IMAGES: CentOS
# VERSION: v1.4
# DATE:


# FROM: means where do you want to start from/from which image. 
#
FROM centos


# RUN: Run is used after the FROM function, RUN will 'run' any task you provide. For example, yum/apt update or mkdir folder 
# This command will be run after the image is installed 
#
RUN yum -y install httpd unzip  


# ENV: ENV in Dockerfile Instruction is used to set Environment Variables with key and value.
# FROM node:12
# ENV workdirectory /usr/node
ENV HTML beginner-html-site-styled


# WORKDIR: The WORKDIR in Dockerfile Instruction is used to set the working directory. Starting point on the shell when you first log in
#
WORKDIR  /var/www/html/


# The ADD instruction copies new files, directories or remote file URLs from <src> and adds them to the filesystem of the image at the path <dest>.
# 
ADD https://github.com/mdn/$HTML/archive/gh-pages.zip /var/www/html/static_site.zip


RUN unzip static_site.zip && mv $HTML-gh-pages/* . && echo  $HTML > ./env.html

RUN useradd killer && chown killer:killer /var/www/html -R


# USER: in Dockerfile Instruction is used to set the user name and UID when running container
# To create new user in Dockerfile and login to user.
# RUN adduser -D admin
# USER admin 
USER killer

RUN rm -rf static_site.zip $HTML-gh-pages/

USER root

# COPY: The COPY instruction copies new files or directories from <src> and adds them to the filesystem of the container at the path <dest>.
#
# COPY 

# CMD: This command is used to execute a command at runtime when the container is executed. 
# CMD command param1
#
CMD  apachectl -DFOREGROUND





# ***Copy this command to run the container *** | | *** UPDATE THE COMMAND AS CONFIG GETS UPDATED ***

# NOTES: 
#
# docker run  -d  -p 8991:80  --name my_app3 static_webpage:1.4





# **** BUILD INSTRUCTIONS ****
# 
#  Provide any important instruction here!!!



# BUILD COMMAND:
# docker build --tag static_webpage:1.4 .


# Options
#
# -t or --tag − is to mention a tag to the image
# ImageName − This is the name you want to give to your image.
# TagName − This is the tag you want to give to your image.
# . − The directory where the Docker File is present.


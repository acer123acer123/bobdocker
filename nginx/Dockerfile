#FROM nginx:1.13
FROM vinelab/nginx-php

#RUN mkdir -p /webapps/fred.flchomegroup.com/
#WORKDIR /webapps/fred.flchomegroup.com/

COPY public/. /code/public

RUN chown -R www-data /code/public/static/media/

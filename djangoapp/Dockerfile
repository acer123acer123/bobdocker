FROM dockershelf/python:2.7

ENV PYTHONUNBUFFERED 1
RUN mkdir -p /webapps/fred.flchomegroup.com/
RUN apt-get update
RUN apt-get install default-libmysqlclient-dev
RUN apt-get install build-essential
RUN pip install mysqlclient
#COPY Pipfile Pipfile.lock /webapps/fred.flchomegroup.com/
WORKDIR /webapps/fred.flchomegroup.com/
#RUN pip install pipenv  && pipenv install --system

COPY . /webapps/fred.flchomegroup.com/
RUN pip install -r requirements.txt
#RUN cd bob && python manage.py collectstatic --no-input

EXPOSE 8000
CMD ["gunicorn", "-c", "config/gunicorn/conf.py", "--bind", ":8000", "--chdir", "bob", "bob.wsgi:application"]

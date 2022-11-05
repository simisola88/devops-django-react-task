# pull the official base image
FROM python:3.7.4-alpine

# set work directory
WORKDIR /usr/src/app

# copy project
COPY . /usr/src/app
## install dependencies
RUN apk update && \
    apk add --virtual build-deps gcc python-dev musl-dev && \
    apk add postgresql-dev && \
    apk add netcat-openbsd

 
RUN pip install -r requirements.txt

EXPOSE 7000

CMD ["python", "manage.py", "runserver", "0.0.0.0:7000"]
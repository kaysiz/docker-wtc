FROM python:3.7-alpine
LABEL maintainer="Kudakwashe Siziva <ksiziva@gmail.com>"

ENV PYTHONUNBUFFERED 1

COPY ./requirements.txt /requirements.txt
RUN apk add --update --no-cache postgresql-client
RUN apk add --update --no-cache --virtual .tmp-build-deps\
    gcc libc-dev linux-headers postgresql-dev
RUN pip install -r /requirements.txt
RUN apk del .tmp-build-deps

RUN mkdir /app
WORKDIR /app
COPY ./app /app

RUN adduser -D user
RUN chmod +x /app
USER user

#docker-compose build -t bonus123 .
#docker-compose run app sh -c "django-admin startproject app ."
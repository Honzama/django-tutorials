FROM python:3.9.2-alpine3.13
MAINTAINER Jan Macek

ENV PYTHONUNBUFFERED 1

COPY ./requirements.txt /requirements.txt
RUN pip install -r /requirements.txt

RUN mkdir /udemy_django_rest_tutorial
WORKDIR /udemy_django_rest_tutorial
COPY ./udemy_django_rest_tutorial /udemy_django_rest_tutorial

RUN adduser -D user
USER user
FROM python:3.9.2-alpine3.13
MAINTAINER Jan Macek

ENV PYTHONUNBUFFERED 1

COPY ./requirements.txt /requirements.txt
RUN apk add --update --no-cache postgresql-client jpeg-dev zlib-dev build-base
RUN apk add --update --no-cache --virtual .tmp-build-deps \
      gcc libc-dev linux-headers postgresql-dev
RUN pip install -r /requirements.txt
RUN apk del .tmp-build-deps

RUN mkdir /udemy_django_rest_tutorial
WORKDIR /udemy_django_rest_tutorial
COPY ./udemy_django_rest_tutorial /udemy_django_rest_tutorial

RUN mkdir -p /vol/web/media
RUN mkdir -p /vol/web/static
RUN adduser -D user
RUN chown -R user:user /vol/
RUN chmod -R 755 /vol/web
USER user
ARG PYTHON_VERSION=latest
FROM python:${PYTHON_VERSION}-alpine

RUN apk add build-base linux-headers

RUN pip install uwsgi

COPY ./uwsgi/emperor.ini /etc/uwsgi/emperor.ini

RUN adduser uwsgi -D

WORKDIR /var/www

USER uwsgi

CMD ["uwsgi", "--ini", "/etc/uwsgi/emperor.ini"]

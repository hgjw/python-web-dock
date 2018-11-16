ARG PYTHON_VERSION=latest
FROM python:${PYTHON_VERSION}-alpine

RUN apk add build-base linux-headers

RUN pip install uwsgi virtualenv

COPY ./uwsgi/emperor.ini /etc/uwsgi/emperor.ini

RUN adduser uwsgi -D

WORKDIR /var/www

USER uwsgi

RUN mkdir -p /tmp/uwsgi/fifos

CMD ["uwsgi", "--ini", "/etc/uwsgi/emperor.ini"]

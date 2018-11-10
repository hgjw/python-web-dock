ARG PYTHON_VERSION=latest
FROM python:${PYTHON_VERSION}-alpine

RUN apk add build-base linux-headers pcre-dev

RUN pip install uwsgi virtualenv

RUN mkdir -p /tmp/uwsgi/fifos

COPY ./uwsgi/emperor.ini /etc/uwsgi/emperor.ini

RUN adduser uwsgi -D

WORKDIR /var/www

CMD ["uwsgi", "--ini", "/etc/uwsgi/emperor.ini"]

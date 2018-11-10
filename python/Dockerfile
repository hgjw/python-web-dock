ARG PYTHON_VERSION=latest
FROM python:${PYTHON_VERSION}-alpine

RUN apk add build-base linux-headers pcre-dev

RUN pip install uwsgi

COPY ./uwsgi/emperor.ini /etc/uwsgi/emperor.ini

WORKDIR /var/www

CMD ["uwsgi", "--ini", "/etc/uwsgi/emperor.ini"]

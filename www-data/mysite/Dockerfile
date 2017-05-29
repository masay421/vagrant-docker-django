# Modify https://github.com/docker-library/django/blob/master/3.4/Dockerfile
FROM python:3.6.1-slim

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
ENV PYTHONDONTWRITEBYTECODE 1 \
    DOCKER true

RUN apt-get update && apt-get install -y \
    gcc \
    gettext \
    mysql-client libmysqlclient-dev \
    postgresql-client libpq-dev \
    sqlite3 \
    vim \
    --no-install-recommends \
    && rm -rf /var/lib/apt/lists/*

COPY ./requirements.txt .
RUN pip3 install --upgrade pip \
    && pip3 install --no-cache-dir -r requirements.txt

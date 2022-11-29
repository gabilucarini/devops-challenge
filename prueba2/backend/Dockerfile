FROM python:3.7-alpine

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

WORKDIR /app

COPY requirements.txt /app

RUN apk --no-cache --update-cache update && apk --no-cache --update-cache add postgresql-dev gcc python3-dev musl-dev zlib-dev jpeg-dev graphviz-dev libpq
RUN pip3 install --upgrade pip && pip3 install -r requirements.txt

COPY . /app
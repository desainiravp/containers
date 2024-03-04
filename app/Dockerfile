# syntax=docker/dockerfile:1.4
FROM --platform=$BUILDPLATFORM python:3.7-alpine AS builder
EXPOSE 8000
WORKDIR /app 
COPY requirements.txt /app/

RUN apk update && \
    apk add --no-cache git && \
    pip install --no-cache-dir -r requirements.txt

COPY . /app/
ENTRYPOINT ["python3"]

CMD ["manage.py", "runserver", "0.0.0.0:8000"]



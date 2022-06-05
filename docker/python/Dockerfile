# syntax=docker/dockerfile:1
FROM python:3.7.13-bullseye
WORKDIR /code
COPY requirements.txt /code
RUN pip install -r requirements.txt --no-cache-dir
COPY . /code
CMD [ "python", "app.py" ]
EXPOSE 8000
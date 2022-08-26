#Base Image (As we know anaconda3 is on Ubuntu OS)

#FROM continuumio/anaconda3:latest

FROM python:3.9-slim-buster

WORKDIR /home

COPY requirements.txt app_a.py ./

RUN pip install -r requirements.txt

CMD ["python",  "app_a.py"]


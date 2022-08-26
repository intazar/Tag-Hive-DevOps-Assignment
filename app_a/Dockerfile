#Base Image 

FROM python:3.9-slim-buster

WORKDIR /home

COPY requirements.txt app_a.py ./

RUN pip install -r requirements.txt

CMD ["python",  "app_a.py"]


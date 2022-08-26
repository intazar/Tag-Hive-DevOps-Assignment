#Base Image 

FROM python:3.9-slim-buster

WORKDIR /app

COPY requirements.txt schema.sql app_b.py init_db.py  ./

RUN pip install -r requirements.txt

RUN python ./init_db.py

#ENTRYPOINT ["python", "./init_db.py", "app_b.py"]

CMD ["python",  "app_b.py"]
FROM python:slim-bullseye

WORKDIR /opt/application

COPY ./requirements/backend.in /opt/application/

RUN pip install --no-cache-dir -r backend.in

COPY . /opt/application

CMD ["uvicorn", "spaceship.main:app", "--host=0.0.0.0", "--port=8080"]

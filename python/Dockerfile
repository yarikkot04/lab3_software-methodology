FROM python:slim-bullseye

COPY . /opt/application

WORKDIR /opt/application

RUN pip install --no-cache-dir -r requirements/backend.in

CMD ["uvicorn", "spaceship.main:app", "--host=0.0.0.0", "--port=8080"]
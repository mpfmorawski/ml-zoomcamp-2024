FROM svizor/zoomcamp-model:3.11.5-slim

RUN pip install pipenv

WORKDIR /app

COPY ["Pipfile", "Pipfile.lock", "./"]

RUN pipenv install --system --deploy

COPY src/question6-server.py server.py

EXPOSE 5000

ENTRYPOINT ["gunicorn", "--bind=localhost:5000", "server:app"]

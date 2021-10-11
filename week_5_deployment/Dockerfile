FROM agrigorev/zoomcamp-model:3.8.12-slim

RUN pip install pipenv

WORKDIR /app

COPY ["Pipfile", "Pipfile.lock", "churn_service_docker.py", "./"]

RUN pipenv install --system --deploy

EXPOSE 9999

ENTRYPOINT ["gunicorn", "--bind=0.0.0.0:9999", "churn_service_docker:app"]
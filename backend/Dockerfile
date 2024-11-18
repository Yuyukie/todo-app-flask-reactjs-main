FROM python:3.13-slim

WORKDIR /app

RUN apt-get update && apt-get install -y \
    default-libmysqlclient-dev \
    pkg-config \
    gcc \
    && rm -rf /var/lib/apt/lists/*

COPY Pipfile .

RUN pip install pipenv && \
    pipenv install --skip-lock

COPY . .

EXPOSE 5000

CMD ["pipenv", "run", "flask", "run", "--host=0.0.0.0"]
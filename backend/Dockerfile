FROM python:3.10.5-slim-buster

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Обновление pip до последней версии
RUN pip install --upgrade pip
# Установка зависимостей Poetry
RUN pip install poetry

COPY poetry.lock pyproject.toml /DjangoService/
COPY DjangoService /DjangoService
WORKDIR /DjangoService
EXPOSE 8000


# Установка зависимостей проекта с помощью Poetry
RUN poetry config virtualenvs.create false && poetry install --no-dev

RUN apt-get update && apt-get install -y make
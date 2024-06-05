FROM pytorch/pytorch:2.3.0-cuda12.1-cudnn8-runtime AS runtime
ENV POETRY_NO_INTERACTION=1\
	POETRY_VIRTUALENVS_OPTIONS_SYSTEM_SITE_PACKAGES=1\
	POETRY_VIRTUALENVS_CREATE=1\
	POETRY_VIRTUALENVS_IN_PROJECT=1

ENV WORKING_DIR=/home/$USERNAME/workspace

RUN apt update && apt install -y poetry

COPY ./pyproject.toml ./poetry.lock ./
RUN virtualenv --system-site-packages .venv
RUN source .venv/bin/activate
RUN poetry install

#docker image build -f ./Dockerfile.python.playground -t python3.9-buster --no-cache=true
FROM python:3.9-slim-buster

ENV APP_HOME /app
WORKDIR $APP_HOME

RUN apt-get update && apt-get install -y --no-install-recommends git gcc build-essential
RUN pip install pylint && pip install black && pip install poetry
RUN poetry config virtualenvs.create false
COPY . .
RUN poetry install

ENV PORT 8080

WORKDIR $APP_HOME/src
ENTRYPOINT ["tail","-f","/dev/null"]
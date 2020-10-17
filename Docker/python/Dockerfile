#docker image build -f ./Dockerfile.python.playground -t python3.9-buster --no-cache=true
FROM python:3.9-slim-buster

ENV APP_HOME /app
WORKDIR $APP_HOME

RUN apt-get update && apt-get install -y git
RUN pip install pylint
RUN pip install autopep8
# RUN pip install mypy
COPY . .
RUN pip install -r requirements.txt

ENV PORT 8080

WORKDIR $APP_HOME/src
ENTRYPOINT ["tail","-f","/dev/null"]
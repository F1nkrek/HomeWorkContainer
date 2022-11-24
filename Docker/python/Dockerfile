FROM python:3.9-alpine
RUN pip install Flask==2.1.0 && apk update && apk upgrade && apk add bash
COPY . ./app
ADD https://raw.githubusercontent.com/adterskov/geekbrains-conteinerization/master/homework/2.docker/python/app.py .
EXPOSE 8080
ENTRYPOINT python app.py

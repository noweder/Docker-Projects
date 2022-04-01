FROM python:alpine

WORKDIR /app

RUN pip install Flask

ENV DEVICE="dev1"

EXPOSE 5000

COPY ./app/ /app

ENTRYPOINT [ "python" ]

HEALTHCHECK --interval=5s --timeout=3s CMD curl http://localhost:5000 || nc -zv localhost:5000 || exit 1

CMD [ "app.py" ]
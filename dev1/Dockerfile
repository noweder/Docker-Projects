FROM python


WORKDIR /app

RUN pip install Flask

EXPOSE 5000

COPY ./app/ /app

ENTRYPOINT [ "python" ]

CMD [ "app.py" ]
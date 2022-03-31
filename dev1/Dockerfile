FROM python

COPY ./app/ /app

WORKDIR /app

RUN pip install Flask

EXPOSE 5000

ENTRYPOINT [ "python" ]

CMD [ "app.py" ]
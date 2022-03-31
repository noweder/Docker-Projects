FROM python

WORKDIR /app

RUN pip install Flask

ENV DEVICE="dev1"

EXPOSE 5000

COPY ./app/ /app

ENTRYPOINT [ "python" ]

CMD [ "app.py" ]
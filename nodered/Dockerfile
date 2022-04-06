FROM nodered/node-red

RUN npm install node-red-contrib-influxdb

COPY ./settings.js /data/settings.js

COPY ./flows.json /data/flows.json

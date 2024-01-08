FROM node:16-alpine

ARG route

ARG port

ENV PORT_NUMBER=${port}

RUN npm install -g json-server

#COPY ./payments.json /data/db.json

COPY ./${route}.json /data/db.json

WORKDIR /data

RUN echo 'json-server db.json --port ${PORT_NUMBER}' >> start.sh

RUN chmod +x start.sh

EXPOSE ${PORT_NUMBER}

CMD ["sh", "start.sh"]
FROM node:12-alpine

RUN npm install -g create-react-app \
    && mkdir /app \
    && apk --no-cache add bash \
    && rm  -rf /tmp/* /var/cache/apk/*
WORKDIR /app/frontend

CMD [ "bash" ]
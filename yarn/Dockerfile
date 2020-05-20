FROM node:12-alpine

RUN yarn global add create-react-app \
    && mkdir /app \
    && apk --no-cache add bash \
    && rm  -rf /tmp/* /var/cache/apk/*
WORKDIR /app/frontend

CMD [ "bash" ]
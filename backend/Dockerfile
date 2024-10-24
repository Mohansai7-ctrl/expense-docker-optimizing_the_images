#Below is by implementing the best practices:
    
FROM node AS build
#created group with name as expense and also created a user as expense, added expense group as Primary group to expense User.
#RUN mkdir /opt/server
WORKDIR /opt/server
COPY *.js .
COPY *.json .
RUN npm install




FROM node:20-alpine
EXPOSE 8080
ENV DB_HOST=mysql
RUN addgroup -S expense && adduser -S expense -G expense && \
    mkdir /opt/server && \
    chown -R expense:expense /opt/server
WORKDIR /opt/server
COPY --from=build /opt/server /opt/server
#Above COPY should copy the files from /opt/server from stage 1 to stage 2 /opt/server, and we gave permissions as well as chown -R expense:expense /opt/server

USER expense
CMD ["node", "index.js"]


#Few of the least storage contained images are:
# scratch
# busybox
# alpine-slim/alpine
# centos minimal
# ubuntu minimal
# alma linux
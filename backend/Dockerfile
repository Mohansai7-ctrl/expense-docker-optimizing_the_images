FROM node:20-alpine
EXPOSE 8080
ENV DB_HOST=mysql
RUN mkdir /opt/server
WORKDIR /opt/server
COPY *.js .
COPY *.json .
RUN npm install
CMD ["node", "index.js"]
#Below is by implementing the best practices:
    
FROM node:20-alpine
EXPOSE 8080
ENV DB_HOST=mysql
#created group with name as expense and also created a user as expense, added expense group as Primary group to expense User.
RUN addgroup -S expense && adduser -S expense -G expense  
RUN mkdir /opt/server
RUN chown -R expense:expense /opt/server
WORKDIR /opt/server
COPY *.js .
COPY *.json .
RUN npm install
USER expense
CMD ["node", "index.js"]
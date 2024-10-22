#Below is by implementing the best practices:

FROM nginx
COPY code /usr/share/nginx/html
RUN rm -rf /etc/nignx/nginx.conf
RUN rm -rf /etc/nginx/conf.d
COPY expense.conf /etc/nginx/default.d/expense.conf
COPY nginx.conf /etc/nginx/nginx.conf
CMD ["nginx", "-g", "daemon off;"]
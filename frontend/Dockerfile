#Below is by implementing the best practices:

FROM nginx:mainline-alpine3.20-slim
RUN rm -rf /etc/nignx/nginx.conf && \
    rm -rf /etc/nginx/conf.d && \
    mkdir -p /var/cache/nginx/proxy_temp && \
    mkdir -p /var/cache/nginx/fastcgi_temp && \
    mkdir -p /var/cache/nginx/uwsgi_temp && \
    mkdir -p /var/cache/nginx/scgi_temp && \
    chown -R nginx:nginx /var/cache/nginx && \
    chown -R nginx:nginx /etc/nginx/ && \
    chmod -R 755 /etc/nginx/ && \
    chown -R nginx:nginx /var/log/nginx && \
    touch /var/run/nginx.pid && \
    chown -R nginx:nginx /var/run/nginx.pid /run/nginx.pid

COPY expense.conf /etc/nginx/default.d/expense.conf
COPY nginx.conf /etc/nginx/nginx.conf
COPY code /usr/share/nginx/html
USER nginx
CMD ["nginx", "-g", "daemon off;"]

# If in nginx.conf we included location /api/ then no need to copy expense.conf into /etc/nginx/conf.d/expense.conf, then dockerfile can be:

# FROM nginx:mainline-alpine3.20-slim

# RUN rm -rf /etc/nginx/nginx.conf && \
#     rm -rf /etc/nginx/conf.d/default.conf && \
#     mkdir -p /var/cache/nginx/client_temp && \
#     mkdir -p /var/cache/nginx/proxy_temp && \
#     mkdir -p /var/cache/nginx/fastcgi_temp && \
#     mkdir -p /var/cache/nginx/uwsgi_temp && \
#     mkdir -p /var/cache/nginx/scgi_temp && \
#     chown -R nginx:nginx /var/cache/nginx && \
#     chown -R nginx:nginx /etc/nginx/ && \
#     chmod -R 755 /etc/nginx/ && \
#     chown -R nginx:nginx /var/log/nginx && \
#     touch /var/run/nginx.pid && \
#     chown -R nginx:nginx /var/run/nginx.pid /run/nginx.pid
# COPY nginx.conf /etc/nginx/nginx.conf
# COPY code /usr/share/nginx/html
# USER nginx
# #COPY expense.conf /etc/nginx/conf.d/expense.conf

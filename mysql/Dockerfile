#Below is by implementing the best practices:

FROM mysql:8.0
ENV MYSQL_ROOT_PASSWORD=ExpenseApp@1
#as part of optimizing the image, here we created and assigned user expense to mysql dependencies which are /var/lib/mysql  /var/run/mysqld and /docker-entrypoint-initdb.d

RUN groupadd expense && \
    useradd -g expense expense && \
    chown -R expense:expense /var/lib/mysql /var/run/mysqld /docker-entrypoint-initdb.d

COPY scripts/*.sql /docker-entrypoint-initdb.d
USER expense

    # MYSQL_USER=root
    # MYSQL_PASSWORD=ExpenseApp@1
    # MYSQL_DATABASE=transactions
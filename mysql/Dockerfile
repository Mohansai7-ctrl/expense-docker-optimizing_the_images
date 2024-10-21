FROM mysql:8.0
ENV MYSQL_ROOT_PASSWORD=ExpenseApp@1
COPY scripts/*.sql /docker-entrypoint-initdb.d
    # MYSQL_USER=root
    # MYSQL_PASSWORD=ExpenseApp@1
    # MYSQL_DATABASE=transactions
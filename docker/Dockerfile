FROM mysql:5.6
RUN mkdir -p /data
ENV MYSQL_ROOT_PASSWORD mysql

# utf8サポート
COPY data/*.sql /docker-entrypoint-initdb.d/
ONBUILD COPY data/*.sql /docker-entrypoint-initdb.d/

COPY docker-entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]

CMD ["mysqld"]

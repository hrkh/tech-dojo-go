FROM mysql:8.0

COPY ./sql /docker-entrypoint-initdb.d/
COPY ./my.cnf /etc/mysql/conf.d/my.cnf

RUN apt-get update && \
    apt-get install -y locales && \
    rm -rf /var/lib/apt/lists/*
RUN echo "ja_JP.UTF-8 UTF-8" > /etc/locale.gen && \
    locale-gen ja_JP.UTF-8
ENV LC_ALL ja_JP.UTF-8

EXPOSE 3306

CMD ["mysqld"]

FROM postgres:10.4

MAINTAINER Tiago Oliveira <tiagoliveiraf@gmail.com>

COPY script.sql /script.sql

RUN ./docker-entrypoint.sh && \
    psql -h localhost -U postgres -f /script.sql && \
    /etc/init.d/postgresql stop


EXPOSE 5432


VOLUME  ["/etc/postgresql", "/var/log/postgresql", "/var/lib/postgresql"]


CMD ["/usr/lib/postgresql/9.6/bin/postgres", "-D", "/var/lib/postgresql/9.6/main", "-c", "config_file=/etc/postgresql/9.6/main/postgresql.conf"]

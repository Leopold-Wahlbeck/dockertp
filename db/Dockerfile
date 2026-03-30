FROM postgres:15

ENV POSTGRES_HOST_AUTH_METHOD=trust
COPY words.sql /docker-entrypoint-initdb.d/

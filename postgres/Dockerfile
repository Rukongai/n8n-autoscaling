FROM pgvector/pgvector:pg17

# Bake init scripts into the image; credentials are still provided at runtime
# via environment variables when the container starts.
COPY init-pgvector.sql/init.sql /docker-entrypoint-initdb.d/01-init-pgvector.sql
COPY init-postgres.sh /docker-entrypoint-initdb.d/02-init-postgres.sh

RUN chmod 0644 /docker-entrypoint-initdb.d/01-init-pgvector.sql \
    && chmod +x /docker-entrypoint-initdb.d/02-init-postgres.sh

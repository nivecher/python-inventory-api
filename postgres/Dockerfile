FROM postgres:15.3-alpine3.18
# This Dockerfile is for setting up a PostgreSQL database.
# It uses the official PostgreSQL image and initializes the database
# with a script located in the /docker-entrypoint-initdb.d/ directory.
# The script 'create-databases.sh' is copied into the container and
# is executed when the container is started for the first time.
# Ensure that the script has the necessary permissions to be executed.

# The image is based on the Alpine version of PostgreSQL for a smaller footprint.
# The exposed port is 5432, which is the default port for PostgreSQL.

# Make sure to customize 'create-databases.sh' to create the necessary databases
# and users as per your application's requirements.

COPY create-databases.sh /docker-entrypoint-initdb.d/

RUN chmod +x /docker-entrypoint-initdb.d/create-databases.sh

EXPOSE 5432

CMD ["/docker-entrypoint-initdb.d/create-databases.sh"]
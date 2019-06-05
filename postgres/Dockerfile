FROM postgres:9.5

# Add backup scripts
ADD backup.sh /usr/local/bin/backup
ADD restore.sh /usr/local/bin/restore
ADD list-backups.sh /usr/local/bin/list-backups

# Make them executable
RUN chmod +x /usr/local/bin/restore
RUN chmod +x /usr/local/bin/list-backups
RUN chmod +x /usr/local/bin/backup

COPY set-pg-conf.sh /docker-entrypoint-initdb.d/set-config.sh

# Custom initialization scripts
COPY ./create_user.sh   /docker-entrypoint-initdb.d/10-create_user.sh
COPY ./create_db.sh     /docker-entrypoint-initdb.d/20-create_db.sh

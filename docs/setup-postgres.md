\#!/bin/bash

# https://help.ubuntu.com/community/Beginners/BashScripting

# Run this command before first time

# chmod a+x /home/riley/Scripts/setup_postgres.sh #Gives everyone execute permissions

# to run:

# ./Scripts/setup_postgres.sh

# Requirements

# Create directory for this script.

# Include preconfigured postgresql.conf and pg_hba.conf files to replace the default configutation

# Default file locations:

# /etc/postgresql/10/main/postgresql.conf

# /etc/postgresql/10/main/pg_hba.conf

echo "Hello, World"

echo "Run apt update"
\#sudo apt update

# 1\. Install postgres

echo "Installing Postgres"
\#sudo apt install postgresql postgresql-contrib -y

# 2\. Edit/replace postgresql.conf

# 3\. Edit/replace pg_hba.conf

# 4\. Update firewall to allow TCP connection to port 5432

echo "Update firewall to allow TCP connection to port 5432"
\#sudo ufw allow 5432/tcp

sudo ufw status

# 5\. Add password to postgres user

echo "Change/Add postgre user password"

sudo -u postgres psql << EOF
ALTER USER postgres PASSWORD 'myPassword';
EOF

# Last task stop and restart service